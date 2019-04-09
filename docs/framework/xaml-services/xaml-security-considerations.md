---
title: Consideraciones de seguridad sobre XAML
ms.date: 03/30/2017
helpviewer_keywords:
- security [XAML Services], .NET XAML services
- XAML security [XAML Services]
ms.assetid: 544296d4-f38e-4498-af49-c9f4dad28964
ms.openlocfilehash: 124310497cc2a8e8a816ba90b2c68a16ed342ae6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59162677"
---
# <a name="xaml-security-considerations"></a>Consideraciones de seguridad sobre XAML
Este tema describe procedimientos recomendados de seguridad en las aplicaciones cuando se usa XAML y API de servicios XAML de .NET Framework.  
  
## <a name="untrusted-xaml-in-applications"></a>XAML que no se confía en las aplicaciones  
 En el sentido más general, XAML no confiable es cualquier origen XAML que su aplicación específicamente no se incluyen ni emitir.  
  
 XAML que está compilado o se almacena como un `resx`-el recurso de tipo dentro de un ensamblado de confianza y firmado no es de confianza inherente. Puede confiar en el XAML como confiar en el ensamblado como un todo. En la mayoría de los casos, le preocupa solo con los aspectos de confianza de XAML flexible, que es un origen de XAML que se carga desde una secuencia u otra E/S. XAML dinámico no es un componente específico o una característica de un modelo de aplicación con una infraestructura de empaquetado y la implementación. Sin embargo, un ensamblado podría implementar un comportamiento que se debe cargar XAML dinámico.  
  
 Para XAML que no se confía, se debería tratar generalmente el mismo como si fuera código no seguro. Use espacio aislado u otras metáforas para impedir que XAML posiblemente no confiable accedan a su código de confianza.  
  
 La naturaleza de las capacidades XAML proporciona el XAML el derecho para construir objetos y establecer sus propiedades. Estas capacidades también incluyen el acceso a los convertidores de tipos, asignación y acceso a los ensamblados en el dominio de aplicación mediante las extensiones de marcado, `x:Code` bloques y así sucesivamente.  
  
 Además de sus capacidades de nivel de lenguaje XAML se usa para la definición de interfaz de usuario en muchas tecnologías. Cargar XAML no confiable podría significar al cargar una interfaz de usuario de suplantación de identidad malintencionado.  
  
## <a name="sharing-context-between-readers-and-writers"></a>Compartir el contexto entre los lectores y escritores  
 La arquitectura de servicios XAML de .NET Framework para los lectores XAML y escritores XAML requiere a menudo compartir un lector XAML a un sistema de escritura XAML o un contexto de esquema XAML compartido. Uso compartido de objetos o contextos puede ser necesario si va a escribir la lógica de bucle de nodo XAML, o proporcionar una personalizada guardar ruta de acceso. No deben compartir las instancias del lector XAML, el contexto de esquema XAML no predeterminado o la configuración de las clases de lector/escritor XAML entre el código de confianza y.  
  
 La mayoría de escenarios y las operaciones que implican la escritura de un tipo basado en CLR de respaldo del objeto XAML solamente pueden usar el contexto de esquema XAML predeterminado. El contexto de esquema XAML predeterminado no incluir explícitamente la configuración que podría poner en peligro la plena confianza. Por lo tanto, es seguro compartir el contexto entre los componentes de lector/escritor XAML sea de confianza y. Sin embargo, si lo hace, es aún una práctica recomendada para mantener estos lectores y escritores independiente <xref:System.AppDomain> ámbitos con una de ellas específicamente prevista o un espacio aislado de confianza parcial.  
  
## <a name="xaml-namespaces-and-assembly-trust"></a>Los espacios de nombres XAML y confianza del ensamblado  
 La sintaxis básica de no completo y la definición de cómo XAML interpreta una asignación de espacio de nombres XAML personalizada a un ensamblado no distingue entre un ensamblado de confianza y que se cargan en el dominio de aplicación. Por lo tanto, es técnicamente posible para un ensamblado de confianza suplantar la identidad de asignación de espacio de nombres XAML prevista del ensamblado de confianza y capturar información de propiedad y objeto declarado de un origen XAML. Si tiene requisitos de seguridad para evitar esta situación, se debe realizar la asignación de espacio de nombres XAML prevista con una de las técnicas siguientes:  
  
-   Utilice un nombre completo del ensamblado con nombre seguro en todas las asignaciones de espacio de nombres XAML realizadas por XAML la aplicación.  
  
-   Restringir la asignación del ensamblado a un conjunto fijo de ensamblados de referencia, mediante la creación de un determinado <xref:System.Xaml.XamlSchemaContext> para el XAML los lectores XAML y los escritores de objetos. Vea <xref:System.Xaml.XamlSchemaContext.%23ctor%28System.Collections.Generic.IEnumerable%7BSystem.Reflection.Assembly%7D%29>.  
  
## <a name="xaml-type-mapping-and-type-system-access"></a>Asignación de tipos XAML y el acceso al sistema de tipo  
 XAML es compatible con su propio sistema de tipos, que en muchos sentidos es igual a cómo CLR implementa el sistema de tipos CLR básico. Sin embargo, ciertos aspectos de reconocimiento de tipo donde se están tomando decisiones de confianza sobre un tipo en función de su información de tipo, debe diferir la información de tipo en lo tipos de respaldo de CLR. Esto es porque algunas de las capacidades de informes específicas del sistema de tipos XAML se dejan abiertos como los métodos virtuales y por lo tanto, no son totalmente bajo el control de las implementaciones de servicios XAML de .NET Framework originales. Estos puntos de extensibilidad existen porque el sistema de tipos XAML es extensible, para que coincida con la extensibilidad de XAML en sí mismo y sus posibles estrategias alternativas de asignación de tipos frente a la implementación de respaldo de CLR predeterminada y el contexto de esquema XAML predeterminado. Para obtener más información, consulte las notas específicas en varias de las propiedades de <xref:System.Xaml.XamlType> y <xref:System.Xaml.XamlMember>.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Xaml.Permissions.XamlAccessLevel>
