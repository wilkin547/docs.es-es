---
title: Consideraciones de seguridad sobre XAML
ms.date: 03/30/2017
helpviewer_keywords:
- security [XAML Services], .NET XAML services
- XAML security [XAML Services]
ms.assetid: 544296d4-f38e-4498-af49-c9f4dad28964
ms.openlocfilehash: 1864910b339c74e3033fb4d6d8baebffada1a4f8
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432921"
---
# <a name="xaml-security-considerations"></a>Consideraciones de seguridad XAML

En este artículo se describen los procedimientos recomendados para la seguridad en las aplicaciones cuando se usa XAML y la API de servicios XAML de .NET.

## <a name="untrusted-xaml-in-applications"></a>XAML que no es de confianza en aplicaciones

En el sentido más general, XAML que no es de confianza es cualquier origen XAML que la aplicación no incluyó o emitió específicamente.

XAML que se compila o `resx`almacena como un recurso de tipo dentro de un ensamblado de confianza y firmado no es inherentemente de confianza. Puede confiar en el XAML tanto como confíe en el ensamblado en su conjunto. En la mayoría de los casos, solo te preocupan los aspectos de confianza de XAML suelto, que es un origen XAML que se carga desde una secuencia u otra E/S. XAML suelto no es un componente específico o característica de un modelo de aplicación con una infraestructura de implementación y empaquetado. Sin embargo, un ensamblado podría implementar un comportamiento que implica cargar XAML suelto.

Para XAML que no es de confianza, debe tratarlo generalmente igual que si fuera código que no es de confianza. Usa el espacio aislado u otras metáforas para evitar que XAML posiblemente no sea de confianza tenga acceso al código de confianza.

La naturaleza de las capacidades XAML da al XAML el derecho de construir objetos y establecer sus propiedades. Estas capacidades también incluyen el acceso a convertidores de tipos, `x:Code` la asignación y el acceso a ensamblados en el dominio de aplicación, mediante extensiones de marcado, bloques, etc.

Además de sus capacidades de nivel de lenguaje, XAML se usa para la definición de interfaz de usuario en muchas tecnologías. Cargar XAML que no es de confianza puede significar cargar una interfaz de usuario de suplantación malintencionada.

## <a name="sharing-context-between-readers-and-writers"></a>Compartir contexto entre lectores y escritores

La arquitectura de servicios XAML de .NET para lectores XAML y escritores XAML a menudo requiere compartir un lector XAML en un escritor XAML o en un contexto de esquema XAML compartido. Es posible que sea necesario compartir objetos o contextos si escribes lógica de bucle de nodo XAML o proporcionas una ruta de acceso de guardado personalizada. No compartas instancias de lector XAML, contexto de esquema XAML no predeterminado ni configuración para clases de lector/escritor XAML entre código de confianza y código que no es de confianza.

La mayoría de los escenarios y operaciones que implican la escritura de objetos XAML para una copia de seguridad de tipos basada en CLR solo pueden usar el contexto de esquema XAML predeterminado. El contexto de esquema XAML predeterminado no incluye explícitamente la configuración que podría poner en peligro la plena confianza. Por lo tanto, es seguro compartir el contexto entre componentes de lector/escritor XAML de confianza y que no son de confianza. Sin embargo, si lo hace, sigue siendo una práctica recomendada <xref:System.AppDomain> mantener a dichos lectores y escritores en ámbitos separados, con uno de ellos específicamente pensado/sandboxed para la confianza parcial.

## <a name="xaml-namespaces-and-assembly-trust"></a>Espacios de nombres XAML y confianza de ensamblado

La sintaxis y definición básicas no calificadas para saber cómo XAML interpreta una asignación de espacio de nombres XAML personalizada a un ensamblado no distingue entre un ensamblado de confianza y no confiable como cargado en el dominio de aplicación. Por lo tanto, es técnicamente posible que un ensamblado que no es de confianza suplantar la asignación de espacio de nombres XAML prevista de un ensamblado de confianza y capturar la información de objeto y propiedad declarada de un origen XAML. Si tiene requisitos de seguridad para evitar esta situación, la asignación de espacio de nombres XAML prevista debe realizarse mediante una de las siguientes técnicas:

- Usa un nombre de ensamblado completo con nombre seguro en cualquier asignación de espacio de nombres XAML realizada por XAML de la aplicación.

- Restringir la asignación de ensamblados a un conjunto <xref:System.Xaml.XamlSchemaContext> fijo de ensamblados de referencia, mediante la construcción de un específico para los lectores XAML y escritores de objetos XAML. Vea <xref:System.Xaml.XamlSchemaContext.%23ctor%28System.Collections.Generic.IEnumerable%7BSystem.Reflection.Assembly%7D%29>.

## <a name="xaml-type-mapping-and-type-system-access"></a>Asignación de tipos XAML y acceso al sistema de tipos

XAML admite su propio sistema de tipos, que en muchos sentidos es un elemento del mismo nivel para cómo CLR implementa el sistema de tipos CLR básico. Sin embargo, para ciertos aspectos de la conciencia de tipo donde está tomando decisiones de confianza sobre un tipo basado en su información de tipo, debe aplazar la información de tipo en los tipos de respaldo de CLR. Esto se debe a que algunas de las capacidades de informes específicas del sistema de tipos XAML se dejan abiertas como métodos virtuales y, por lo tanto, no están totalmente bajo el control de las implementaciones originales de servicios XAML de .NET. Estos puntos de extensibilidad existen porque el sistema de tipos XAML es extensible, para que coincida con la extensibilidad del propio XAML y sus posibles estrategias alternativas de asignación de tipos frente a la implementación respaldada por CLR predeterminada y el contexto de esquema XAML predeterminado. Para obtener más información, consulte las notas <xref:System.Xaml.XamlType> <xref:System.Xaml.XamlMember>específicas sobre varias de las propiedades de y .

## <a name="see-also"></a>Consulte también

- <xref:System.Xaml.Permissions.XamlAccessLevel>
