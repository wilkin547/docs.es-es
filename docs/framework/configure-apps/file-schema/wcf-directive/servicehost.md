---
title: "@ServiceHost | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 96ba6967-00f2-422f-9aa7-15de4d33ebf3
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# @ServiceHost
Asocia el generador usado para crear el host del servicio con el servicio que se va a hospedar y otros aspectos de programación necesarios para tener acceso o compilar el código de hospedaje proporcionado en el archivo .svc.  
  
## Sintaxis  
  
```  
  
<% @ServiceHost   
Service = "Service, ServiceNamespace"   
Factory = "Factory, FactoryNamespace"  
Debug = "Debug"  
Language = "Language"   
CodeBehind = "CodeBehind"%>  
```  
  
## Atributos  
  
#### Servicio  
 El nombre del tipo de CLR del servicio hospedado.  Esto debería ser un nombre completo de un tipo que implementa uno o varios contactos del servicio.  
  
#### Factory  
 El nombre de tipo de CLR del generador de host de servicio usado para crear instancias del host del servicio.  Este atributo es opcional.  Si no se especifica, se usa el valor predeterminado <xref:System.ServiceModel.Activation.ServiceHostFactory> que devuelve una instancia de <xref:System.ServiceModel.ServiceHost>.  
  
#### Depurar  
 Indica si el servicio de [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] debe compilarse con símbolos de depuración.  Es `true` si el servicio de [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] debe compilarse con símbolos de depuración; de lo contrario, es `false`.  
  
#### Lenguaje  
 Especifica el lenguaje usado al compilar todo el código en línea del archivo \(.svc\).  Los valores pueden representar cualquier lenguaje compatible con .NET, incluyendo C\#, VB y JS, que hacen referencia a C\#, Visual Basic .NET y JScript .NET, respectivamente.  Este atributo es opcional.  
  
#### CodeBehind  
 Especifica el archivo de código fuente que implementa el servicio Web XML, cuando la clase que implementa dicho servicio no reside en el mismo archivo, y no se ha compilado en un ensamblado ni se ha colocado en el directorio \\Bin.  
  
## Comentarios  
 <xref:System.ServiceModel.ServiceHost> usado para hospedar el servicio es un punto de extensibilidad dentro del modelo de programación de [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].  Se usa un patrón del generador para crear <xref:System.ServiceModel.ServiceHost> porque es, potencialmente, un tipo polimórfico del que el entorno de hospedaje no debería crear instancias directamente.  
  
 las implementaciones predeterminadas usan <xref:System.ServiceModel.Activation.ServiceHostFactory> para crear una instancia de <xref:System.ServiceModel.ServiceHost>.  Pero puede proporcionar su propio generador \(uno que devuelve su host derivado\) especificando el nombre de tipo de CLR de su implementación del generador en la directiva [@ServiceHost](../../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md).  
  
 Para usar su generador de host de servicios personalizados propio en lugar del generador predeterminado, simplemente proporcione el nombre de tipo en la directiva [@ServiceHost](../../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) de la forma siguiente:  
  
```  
<% @ServiceHost Factory=”DerivedFactory” Service=”MyService” %>  
```  
  
 Mantenga las implementaciones del generador tan ligeras como sea posible.  Si tiene mucha lógica personalizada, su código es más reutilizable si coloca esa lógica dentro de su host en lugar de dentro del generador.  
  
 Por ejemplo, para habilitar un extremo con AJAX habilitado para `MyService`, especifique <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> para el valor del atributo `Factory`, en lugar de valor predeterminado <xref:System.ServiceModel.Activation.ServiceHostFactory>, en la directiva [@ServiceHost](../../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) como se muestra en el siguiente ejemplo.  
  
## Ejemplo  
  
```  
<% @ServiceHost   
Service="MyService"  
Language="C#"  
Debug="true"  
Factory="WebScriptServiceHostFactory"  
%>  
```  
  
## Vea también  
 [Host de servicio personalizado](../../../../../docs/framework/wcf/samples/custom-service-host.md)