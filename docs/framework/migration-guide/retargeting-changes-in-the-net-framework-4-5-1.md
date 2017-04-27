---
title: "Cambios de redestinación en .NET Framework 4.5.1 | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application compatibility
- retargeting changes
- .NET Framework 4.5.1
- retargeting changes, .NET Framework 4.5.1
- retargeting changes, .NET Framework
ms.assetid: 8087326d-77e9-4804-ba33-ff1bb1bec2b8
caps.latest.revision: 15
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 0c497561254c0f97f22ac05c7d44224b30ef74d0
ms.lasthandoff: 04/18/2017

---
# <a name="retargeting-changes-in-the-net-framework-451"></a>Cambios de redestinación en .NET Framework 4.5.1
En algunos pocos casos, los cambios de redestinación pueden afectar a las aplicaciones que se vuelven a compilar para [!INCLUDE[net_v451](../../../includes/net-v451-md.md)]. No afectan a los binarios que tienen como destino una versión anterior de .NET Framework pero que se ejecutan en la versión 4.5.1. [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] incluye cambios de redestinación en las áreas siguientes:  
  
-   [Principal](#Core)  
  
-   [ADO.NET](#ADO)  
  
-   [MSBuild](#MSBuild)  
  
 La columna de ámbito de las tablas siguientes especifica la importancia de cada cambio:  
  
-   Principal. Cambio significativo que afecta a un gran número de aplicaciones o que requiere una modificación sustancial del código. Observe que ninguno de los cambios de redestinación pertenecen a esta categoría.  
  
-   Secundario. Cambio que afecta a un pequeño número de aplicaciones o que requiere ligeras modificaciones en el código.  
  
-   Avanzado. Cambio que afecta a aplicaciones de escenarios muy concretos que no son frecuentes.  
  
-   Transparente. Cambio que no tiene ningún efecto apreciable en el programador o el usuario de la aplicación. No es necesario modificar la aplicación debido a este cambio.  
  
<a name="Core"></a>   
## <a name="core-retargeting-changes"></a>Cambios principales de redestinación  
  
|Característica|Cambio|Impacto|Ámbito|  
|-------------|------------|------------|-----------|  
|Atributo <xref:System.ObsoleteAttribute?displayProperty=fullName>|Cuando crea una biblioteca de metadatos de Windows (archivo .winmd), el atributo <xref:System.ObsoleteAttribute> se exporta como <xref:System.ObsoleteAttribute> y [Windows.Foundation.DeprecatedAttribute](http://msdn.microsoft.com/library/windows/apps/windows.foundation.metadata.deprecatedattribute.aspx).|Volver a compilar el código fuente existente que use el atributo <xref:System.ObsoleteAttribute> puede generar advertencias al usar dicho código desde C++/CX o JavaScript.<br /><br /> No se recomienda aplicar <xref:System.ObsoleteAttribute> y [Windows.Foundation.DeprecatedAttribute](http://msdn.microsoft.com/library/windows/apps/windows.foundation.metadata.deprecatedattribute.aspx) al código en los ensamblados administrados; se podrían producir advertencias de compilación.<br /><br /> Para más información, vea el tema de referencia <xref:System.ObsoleteAttribute>.|Borde|  
  
<a name="ADO"></a>   
## <a name="adonet-retargeting-changes"></a>Cambios de redestinación de ADO.NET  
  
|Característica|Cambio|Impacto|Ámbito|  
|-------------|------------|------------|-----------|  
|<xref:System.Data.Common.DbParameter?displayProperty=fullName> class|<xref:System.Data.Common.DbParameter.Precision%2A?displayProperty=fullName> and <xref:System.Data.Common.DbParameter.Scale%2A?displayProperty=fullName> are implemented as public virtual properties. Reemplazan las implementaciones de interfaz explícita correspondientes, <xref:System.Data.Common.DbParameter.System%23Data%23IDbDataParameter%23Precision%2A?displayProperty=fullName> y <xref:System.Data.Common.DbParameter.System%23Data%23IDbDataParameter%23Scale%2A?displayProperty=fullName>.|El cambio solo afecta a los desarrolladores que compilan un proveedor de bases de datos de ADO.NET.|Avanzado|  
  
<a name="MSBuild"></a>   
## <a name="msbuild-retargeting-changes"></a>Cambios de redestinación de MSBuild  
  
|Característica|Cambio|Impacto|Ámbito|  
|-------------|------------|------------|-----------|  
|Tarea `ResolveAssemblyReference`|La tarea emite una advertencia, MSB3270, que indica que una referencia o cualquiera de sus dependencias no coincide con la arquitectura de la aplicación. Por ejemplo, esto ocurre si una aplicación compilada con la opción `anycpu` incluye una referencia a x86. Este tipo de escenario podría producir un error de la aplicación en tiempo de ejecución (en este caso, si la aplicación se implementa como un proceso x64).|Existen dos áreas de impacto:<br /><br /> -   Una nueva compilación genera advertencias que no aparecieron al compilar la aplicación con una versión anterior de MSBuild. Sin embargo, dado que la advertencia identifica un posible origen de errores en el runtime, se debe investigar y solucionar.<br />-   Si las advertencias se tratan como errores, la aplicación no se compilará.|Secundaria|  
  
## <a name="see-also"></a>Vea también  
 [Cambios en el tiempo d ejecución](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-5-1.md)   
 [Compatibilidad de aplicaciones en 4.5](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5.md)   
 [Compatibilidad de aplicaciones en 4.5.2](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5-2.md)
