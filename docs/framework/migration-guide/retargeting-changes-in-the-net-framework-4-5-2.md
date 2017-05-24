---
title: "Cambios de redestinación en .NET Framework 4.5.2 | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2be2a828-9052-4738-a965-d4a836cc6384
caps.latest.revision: 5
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 10af942724ce0207bc6e64f1ebabfdcd2d3488bd
ms.contentlocale: es-es
ms.lasthandoff: 05/22/2017

---
# <a name="retargeting-changes-in-the-net-framework-452"></a>Cambios de redestinación en .NET Framework 4.5.2
En casos poco frecuentes, los cambios de redestinación pueden afectar a las aplicaciones que se vuelven a compilar para .NET Framework 4.5.2. A menos que se especifique lo contrario en las tablas siguientes, estos cambios no afectan a los archivos binarios que tienen como destino una versión anterior de .NET Framework pero que se ejecutan en la versión 4.5.2. .NET Framework 4.5.2 incluye cambios de redestinación en las áreas siguientes:  
  
-   [Entity Framework](#EF)  
  
-   [Windows Forms](#WinForms)  
  
<a name="EF"></a>   
## <a name="entity-framework-retargeting-changes"></a>Cambios de redestinación de Entity Framework  
  
|Característica|Cambio|Impacto|Ámbito|  
|-------------|------------|------------|-----------|  
|Consultas más sencillas al usar operaciones de limitación sin ordenar|Las consultas que producen instrucciones de `JOIN` y contienen una llamada a una operación de limitación sin usar primero <xref:System.Data.Objects.ObjectQuery%601.OrderBy%2A>, ahora producen un código SQL más sencillo. Después de actualizar a [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], estas consultas producían código SQL más complicado que en versiones anteriores.|Esta característica está deshabilitada de manera predeterminada. Si Entity Framework genera instrucciones de `JOIN` adicionales que causan una degradación del rendimiento, puede habilitar esta característica; para ello, agregue la entrada siguiente en la sección `<appSettings>` del archivo de configuración de la aplicación (app.config):<br /><br /> `<add key="EntityFramework_SimplifyLimitOperations" value="true" />`|Secundaria|  
  
<a name="WinForms"></a>   
## <a name="windows-forms-retargeting-changes"></a>Cambios de redestinación de Windows Forms  
  
|Característica|Cambio|Impacto|Ámbito|  
|-------------|------------|------------|-----------|  
|Recuperar datos en formato HTML desde el Portapapeles con el método <xref:System.Windows.Forms.DataObject.GetData%2A?displayProperty=fullName>|Para aplicaciones que tienen como destino [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] o que se ejecutan en .NET Framework 4.5.1 o versiones anteriores, <xref:System.Windows.Forms.DataObject.GetData%2A?displayProperty=fullName> recupera datos con formato HTML como una cadena ASCII. Como resultado, los caracteres que no son ASCII (cuyos códigos ASCII son mayores que 0x7F) se representan mediante dos caracteres aleatorios. Por ejemplo, é (0xE9) se representa mediante Ã© (0xC3 0xA9).<br /><br /> Para aplicaciones que tienen como destino [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] o posterior y que se ejecutan en .NET Framework 4.5.2, <xref:System.Windows.Forms.DataObject.GetData%2A?displayProperty=fullName> recupera datos con formato HTML como UTF-8, que representa correctamente caracteres mayores que 0x7F.|Si implementa una solución alternativa para el problema de codificación mediante cadenas con formato HTML (por ejemplo, si codifica de manera explícita la cadena HTML recuperada del Portapapeles y la transfiere al método <xref:System.Text.UTF8Encoding.GetString%2A?displayProperty=fullName>) y cambia el destino de la aplicación de la versión 4 a la versión 4.5, se eliminará dicha solución alternativa.|Secundaria|  
  
## <a name="see-also"></a>Vea también  
 [Cambios en el tiempo d ejecución](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-5-2.md)   
 [Compatibilidad de aplicaciones en 4.5](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5.md)   
 [Compatibilidad de aplicaciones en 4.5.1](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5-1.md)
