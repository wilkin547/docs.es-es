---
title: "XAML Security Considerations | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "security [XAML Services], .NET XAML services"
  - "XAML security [XAML Services]"
ms.assetid: 544296d4-f38e-4498-af49-c9f4dad28964
caps.latest.revision: 7
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 7
---
# XAML Security Considerations
En este tema se describen los procedimientos recomendados para la seguridad en las aplicaciones al usar XAML y la API de los Servicios XAML de .NET Framework.  
  
## XAML que no es de confianza en aplicaciones  
 En el sentido más general, XAML que no es de confianza es cualquier origen XAML que su aplicación no ha incluido o emitido específicamente.  
  
 El XAML compilado o almacenado como un recurso de tipo `resx` dentro de un ensamblado de confianza y con signo no carece de confianza de forma intrínseca.  Puede confiar en el XAML tanto como confíe en el ensamblado en conjunto.  En la mayoría de los casos, se hace referencia únicamente los aspectos de confianza del XAML dinámico, que es un origen XAML que se carga desde una secuencia u otra E\/S.  El XAML dinámico no es un componente o una característica concreta de un modelo de aplicaciones con una infraestructura de implementación y empaquetado.  Sin embargo, un ensamblado podría implementar un comportamiento que implique la carga de XAML dinámico.  
  
 Para XAML que no es de confianza, debería tratarlo generalmente igual que si fuera código que no es de confianza.  Utilice un espacio aislado u otras metáforas para evitar que XAML que posiblemente no sea de confianza tenga acceso a su código de confianza.  
  
 La naturaleza de capacidades de XAML concede al XAML el derecho de construir objetos y establecer sus propiedades.  Esta funcionalidad también incluye el acceso a los convertidores de tipos, la asignación y acceso a los ensamblados en el dominio de aplicación, el uso de las extensiones de marcado, los bloques `x:Code`, etc.  
  
 Además de sus funciones de nivel de lenguaje, el XAML se utiliza para la definición de la interfaz de usuario en muchas tecnologías.  Cargar XAML que no es de confianza podría significar cargar una interfaz de usuario malintencionada de suplantación de identidad.  
  
## Compartir el contexto entre los lectores y escritores  
 La arquitectura de los Servicios XAML de .NET Framework para los lectores y sistemas de escritura de XAML requieren a menudo compartir un lector de XAML con un sistemas de escritura de XAML, o un contexto de esquema XAML compartido.  Podría ser necesario compartir los objetos o contextos si está escribiendo la lógica de bucle de nodo XAML o proporcionando una ruta de acceso de guardar personalizada.  No debería compartir las instancias de lector de XAML, el contexto de esquema XAML no predeterminado ni los valores de las clases de lector o escritor de XAML entre código confiable y no confiable.  
  
 La mayoría de los escenarios y operaciones que implican la escritura de objetos XAML para un respaldo de los tipos basados en CLR simplemente pueden usar el contexto de esquema XAML predeterminado.  El contexto de esquema XAML predeterminado no incluye explícitamente los valores que podrían poner en peligro la plena confianza.  Así es seguro compartir el contexto entre los componentes de lector y escritor de XAML confiable y no confiable.  Sin embargo, si hace esto, un procedimiento recomendado sigue siendo mantener tales lectores y escritores en los ámbitos de <xref:System.AppDomain> independientes, con uno de ellos específicamente pensado o aislado en un espacio para la confianza parcial.  
  
## Espacios de nombres XAML y confianza de ensamblado  
 La sintaxis no calificada básica y la definición de cómo XAML interpreta una asignación de espacio de nombres XAML personalizada para un ensamblado no distinguen entre un ensamblado confiable y uno no confiable cuando se carga en el dominio de aplicación.  En consecuencia, es técnicamente posible que un ensamblado que no es de confianza suplante la asignación del espacio de nombres XAML intencional de un ensamblado confiable y capture el objeto declarado y la información de propiedad de un origen XAML.  Si tiene requisitos de seguridad para evitar esta situación, su asignación de espacio de nombres XAML intencional se debería realizar mediante una de las siguientes técnicas:  
  
-   Use un nombre de ensamblado completo con un nombre seguro para cualquier asignación de espacio de nombres XAML realizada por el XAML de su aplicación.  
  
-   Restrinja la asignación del ensamblado a un conjunto fijo de ensamblados de referencia, construyendo un <xref:System.Xaml.XamlSchemaContext> concreto para sus lectores de XAML y escritores de objetos XAML.  Vea <xref:System.Xaml.XamlSchemaContext.%23ctor%28System.Collections.Generic.IEnumerable%7BSystem.Reflection.Assembly%7D%29>.  
  
## Asignación de tipos de XAML y acceso al sistema de tipos  
 XAML proporciona soporte técnico para su propio sistema de tipos, que es igual de muchas maneras a la forma en que CLR implementa el sistema de tipos CLR básico.  Sin embargo, para ciertos aspectos del conocimiento de tipos donde se están tomando decisiones de confianza sobre un tipo en función de su información de tipo, debería diferir a la información de tipo en los tipos de respaldo de CLR.  Esto se debe a que algunas de las capacidades de informe concretas del sistema de tipos XAML se quedan abiertas como métodos virtuales y, en consecuencia, no están totalmente bajo el control de las implementaciones originales de los Servicios XAML de .NET Framework.  Estos puntos de extensibilidad existen porque el sistema de tipos XAML es extensible, para coincidir con la extensibilidad del propio XAML y sus posibles estrategias de asignación de tipos alternativa, frente a la implementación respaldada por CLR predeterminada y el contexto de esquema XAML predeterminado.  Para obtener más información, vea las notas específicas sobre varias de las propiedades de <xref:System.Xaml.XamlType> y <xref:System.Xaml.XamlMember>.  
  
## Vea también  
 <xref:System.Xaml.Permissions.XamlAccessLevel>