---
title: "Cambios en tiempo de ejecuci&#243;n en .NET Framework 4.5.2 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 94ac01ea-8b12-44d2-b12b-5220a5d14d87
caps.latest.revision: 5
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 5
---
# Cambios en tiempo de ejecuci&#243;n en .NET Framework 4.5.2
En casos poco frecuentes, los cambios en tiempo de ejecución pueden afectar a las aplicaciones existentes que tienen como destino versiones anteriores de .NET Framework, pero que se ejecutan en el runtime de .NET Framework 4.5.2. Incluyen cambios en las áreas siguientes:  
  
-   [ASP.NET](#ASP_NET)  
  
-   [Entity Framework](#EF)  
  
<a name="ASP_NET"></a>   
## Cambios en tiempo de ejecución de ASP.NET  
  
|Característica|Cambio|Impacto|Ámbito|  
|--------------------|------------|-------------|------------|  
|Atributo `enableViewStateMac` del [elemento de páginas](http://msdn.microsoft.com/es-es/4123bb66-3fe4-4d62-b70e-33758656b458)|ASP.NET ya no permite a los desarrolladores especificar:<br /><br /> `<pages enableViewStateMac="false" />`<br /><br /> O bien<br /><br /> `<@Page EnableViewStateMac="false" %>`|El código de autenticación de mensajes \(MAC\) de estado de vista ahora es obligatorio para todas las solicitudes con estado de vista integrado. Esto solo afecta a las aplicaciones que establecen de manera explícita la propiedad <xref:System.Web.UI.Page.EnableViewStateMac%2A> en `false`.<br /><br /> Para obtener más información, consulte [Resolución de errores de código de autenticación de mensajes \(MAC\) del estado de la vista](http://support.microsoft.com/kb/2915218).|Major|  
  
<a name="EF"></a>   
## Cambios en tiempo de ejecución de Entity Framework  
  
|Característica|Cambio|Impacto|Ámbito|  
|--------------------|------------|-------------|------------|  
|Relaciones mediante una QueryView|Entity Framework ya no produce la excepción <xref:System.StackOverflowException> cuando una aplicación ejecuta una consulta que usa QueryView con una propiedad de navegación 0..1 que intenta incluir las entidades relacionadas como parte de la consulta \(por ejemplo, mediante una llamada a `.Include(e=>e.RelatedNavProp)`\).|Este cambio solo afecta a código que usa QueryViews con relaciones de 1\-0..1 cuando las consultas que se ejecutan realizan llamadas a `.Include`. Mejora la fiabilidad y debe ser transparente para casi todas las aplicaciones. Pero puede deshabilitarlo si causa un comportamiento inesperado; para ello, agregue la entrada siguiente a la sección `<appSettings>` del archivo de configuración de la aplicación:<br /><br /> `<add key="EntityFramework_SimplifyUserSpecifiedViews"  value="false" />`|Borde|  
  
## Vea también  
 [Cambios de redestinación](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-5-2.md)   
 [Compatibilidad de aplicaciones en 4.5](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5.md)   
 [Compatibilidad de aplicaciones en 4.5.1](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5-1.md)