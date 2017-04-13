---
title: "Mitigaci&#243;n: AuthorizationContext predeterminado | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6cfeee63-b148-429a-a7e6-6fe9b0cb7610
caps.latest.revision: 3
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 3
---
# Mitigaci&#243;n: AuthorizationContext predeterminado
La implementación del <xref:System.IdentityModel.Policy.AuthorizationContext> devuelto por una llamada a la <xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext%28System.Collections.Generic.IList%7BSystem.IdentityModel.Policy.IAuthorizationPolicy%7D%29> con un argumento `null` `authorizationPolicies` ha cambiado su implementación en el [!INCLUDE[net_v46](../../../includes/net-v46-md.md)].  
  
## Impacto  
 En raras ocasiones, las aplicaciones WCF que usan la autenticación personalizada pueden sufrir diferencias de comportamiento.  
  
## Mitigación  
 Puede restaurar el comportamiento anterior de dos maneras:  
  
-   Vuelva a compilar la aplicación para que se dirija a una versión anterior a .NET Framework 4.6.  Para los servicios hospedados en IIS, use el elemento `<httpRuntime targetFramework="x.x" />` para que se dirija a una versión anterior de .NET Framework.  
  
-   Agregue la siguiente línea a la sección `<appSettings>` del archivo app.config:  
  
    ```  
    <add key="appContext.SetSwitch:Switch.System.IdentityModel.EnableCachedEmptyDefaultAuthorizationContext" value="true" />  
    ```  
  
## Vea también  
 [Cambios de redestinación](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)