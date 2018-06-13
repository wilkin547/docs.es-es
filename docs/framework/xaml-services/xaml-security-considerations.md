---
title: Consideraciones de seguridad sobre XAML
ms.date: 03/30/2017
helpviewer_keywords:
- security [XAML Services], .NET XAML services
- XAML security [XAML Services]
ms.assetid: 544296d4-f38e-4498-af49-c9f4dad28964
ms.openlocfilehash: ef47e7e370082a2050406710edcb62d0967df8ef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33562367"
---
# <a name="xaml-security-considerations"></a>Consideraciones de seguridad sobre XAML
En este tema describe las prácticas recomendadas para la seguridad en las aplicaciones cuando se usa XAML y API de servicios XAML de .NET Framework.  
  
## <a name="untrusted-xaml-in-applications"></a>XAML no es de confianza en las aplicaciones  
 En el sentido más general, XAML no es de confianza es cualquier origen XAML que su aplicación no específicamente no incluir o emitir.  
  
 XAML que está compilado o almacenado como un `resx`-el recurso de tipo de un ensamblado de confianza y firmado no es intrínsecamente no es de confianza. Puede confiar en el XAML tanto como confíe en el ensamblado como un todo. En la mayoría de los casos, solo esté interesado en los aspectos de confianza de XAML dinámico, que es un origen XAML que se carga desde una secuencia u otra E/S. XAML dinámico no es un componente específico o una característica de un modelo de aplicación con una infraestructura de empaquetado y distribución. Sin embargo, un ensamblado puede implementar un comportamiento que implica cargar XAML dinámico.  
  
 Para XAML que no se confía, debes tratarla generalmente el mismo como si fuera código no seguro. Usar un espacio aislado u otras metáforas para evitar que XAML que posiblemente no se confía tener acceso al código de confianza.  
  
 La naturaleza de las capacidades XAML concede al XAML el derecho a construir objetos y establecer sus propiedades. Estas capacidades son también el acceso a los convertidores de tipos, asignación y obtener acceso a los ensamblados en el dominio de aplicación, con las extensiones de marcado, `x:Code` bloques y así sucesivamente.  
  
 Además de sus capacidades de nivel de lenguaje, XAML se usa para la definición de interfaz de usuario en muchas tecnologías. Cargar XAML no es de confianza, podría significar cargar una interfaz de usuario de suplantación de identidad malintencionado.  
  
## <a name="sharing-context-between-readers-and-writers"></a>Compartir el contexto entre los lectores y escritores  
 La arquitectura de servicios XAML de .NET Framework para los lectores y escritores de XAML requiere a menudo compartir un lector de XAML para un escritor de XAML o un contexto de esquema XAML compartido. Podría ser necesario compartir los objetos o contextos si está escribiendo la lógica de bucle de nodo XAML o proporcionando un personalizado guardar la ruta de acceso. No se deben compartir instancias del lector de XAML, el contexto de esquema XAML no predeterminado o la configuración de las clases de lector/escritor XAML entre el código de confianza y.  
  
 La mayoría de escenarios y las operaciones que implican la escritura de un tipo basado en CLR realizar una copia de objetos XAML solamente pueden usar el contexto de esquema XAML predeterminado. El contexto de esquema XAML predeterminado no incluye explícitamente la configuración que podría poner en peligro la plena confianza. Por lo tanto es seguro compartir el contexto entre los componentes de lector/escritor XAML confiable y no confiables. Sin embargo, si lo hace, sigue siendo un procedimiento recomendado mantener tales lectores y escritores en independiente <xref:System.AppDomain> ámbitos, con uno de ellos específicamente deseada o en un espacio aislado de confianza parcial.  
  
## <a name="xaml-namespaces-and-assembly-trust"></a>Espacios de nombres XAML y confianza del ensamblado  
 La sintaxis sin calificar básica y la definición de cómo XAML interpreta una asignación de espacio de nombres XAML personalizada a un ensamblado no distingue entre un ensamblado de confianza y que se carga en el dominio de aplicación. Por lo tanto, es técnicamente posible para un ensamblado de confianza suplantar la asignación de espacio de nombres XAML intencional de un ensamblado de confianza y capturar información de propiedad y objeto declarado un origen XAML. Si tiene requisitos de seguridad para evitar esta situación, su asignación de espacio de nombres XAML intencional se debería realizar mediante una de las técnicas siguientes:  
  
-   Utilice un nombre completo del ensamblado con nombre seguro en cualquier asignación de espacio de nombres XAML realizada por el XAML de su aplicación.  
  
-   Restringir la asignación del ensamblado a un conjunto fijo de ensamblados de referencia, mediante la creación de un determinado <xref:System.Xaml.XamlSchemaContext> para el código XAML los lectores XAML y los escritores de objetos. Vea <xref:System.Xaml.XamlSchemaContext.%23ctor%28System.Collections.Generic.IEnumerable%7BSystem.Reflection.Assembly%7D%29>.  
  
## <a name="xaml-type-mapping-and-type-system-access"></a>Asignación de tipos XAML y acceso al sistema de tipo  
 XAML es compatible con su propio sistema de tipos, que en muchos aspectos del mismo nivel para el modo en que CLR implementa el sistema de tipos CLR básico. Sin embargo, para ciertos aspectos del conocimiento de tipos donde tome decisiones de confianza sobre un tipo en función de su información de tipo, debe respetar la información de tipo en lo tipos de respaldo de CLR. Esto es porque algunas de las funciones de informes específicas del sistema de tipos XAML se quedan abiertas como métodos virtuales y por lo tanto, no son totalmente bajo el control de las implementaciones de servicios XAML de .NET Framework originales. Estos puntos de extensibilidad existen porque el sistema de tipos XAML es extensible, para que coincida con la extensibilidad del propio XAML y sus posibles estrategias de asignación de tipos alternativas frente a la implementación de respaldada por CLR predeterminada y el contexto de esquema XAML predeterminado. Para obtener más información, consulte las notas específicas en algunas de las propiedades de <xref:System.Xaml.XamlType> y <xref:System.Xaml.XamlMember>.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Xaml.Permissions.XamlAccessLevel>
