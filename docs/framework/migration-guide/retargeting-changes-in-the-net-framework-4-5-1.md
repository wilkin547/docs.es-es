---
title: "Cambios de redestinaci&#243;n en .NET Framework 4.5.1 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8087326d-77e9-4804-ba33-ff1bb1bec2b8
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# Cambios de redestinaci&#243;n en .NET Framework 4.5.1
En algunos pocos casos, los cambios de redestinación pueden afectar a las aplicaciones que se vuelven a compilar para [!INCLUDE[net_v451](../../../includes/net-v451-md.md)]. No afectan a los binarios que tienen como destino una versión anterior de .NET Framework pero que se ejecutan en la versión 4.5.1.[!INCLUDE[net_v451](../../../includes/net-v451-md.md)] incluye cambios de redestinación en las áreas siguientes:  
  
-   [Principal](#Core)  
  
-   [ADO.NET](#ADO)  
  
-   [MSBuild](#MSBuild)  
  
 La columna de ámbito de las tablas siguientes especifica la importancia de cada cambio:  
  
-   Principal. Cambio significativo que afecta a un gran número de aplicaciones o que requiere una modificación sustancial del código. Observe que ninguno de los cambios de redestinación pertenecen a esta categoría.  
  
-   Secundario. Cambio que afecta a un pequeño número de aplicaciones o que requiere ligeras modificaciones en el código.  
  
-   Avanzado. Cambio que afecta a aplicaciones de escenarios muy concretos que no son frecuentes.  
  
-   Transparente. Cambio que no tiene ningún efecto apreciable en el programador o el usuario de la aplicación. No es necesario modificar la aplicación debido a este cambio.  
  
<a name="Core"></a>   
## Cambios principales de redestinación  
  
|Característica|Cambio|Impacto|Ámbito|  
|--------------------|------------|-------------|------------|  
|Atributo <xref:System.ObsoleteAttribute?displayProperty=fullName>|Cuando se crea una biblioteca de metadatos de Windows \(archivo .winmd\), el atributo <xref:System.ObsoleteAttribute> se exporta como <xref:System.ObsoleteAttribute> y como [Windows.Foundation.DeprecatedAttribute](http://msdn.microsoft.com/library/windows/apps/windows.foundation.metadata.deprecatedattribute.aspx).|Volver a compilar el código fuente existente que usa el atributo <xref:System.ObsoleteAttribute> puede generar advertencias al utilizar ese código desde C\+\+\/CX o JavaScript.<br /><br /> No se recomienda aplicar <xref:System.ObsoleteAttribute> y [Windows.Foundation.DeprecatedAttribute](http://msdn.microsoft.com/library/windows/apps/windows.foundation.metadata.deprecatedattribute.aspx) al código en los ensamblados administrados; se podrían producir advertencias de compilación.<br /><br /> Para obtener más información, vea el tema de referencia <xref:System.ObsoleteAttribute>.|Avanzado|  
  
<a name="ADO"></a>   
## Cambios de redestinación de ADO.NET  
  
|Característica|Cambio|Impacto|Ámbito|  
|--------------------|------------|-------------|------------|  
|Clase <xref:System.Data.Common.DbParameter?displayProperty=fullName>|<xref:System.Data.Common.DbParameter.Precision%2A?displayProperty=fullName> y <xref:System.Data.Common.DbParameter.Scale%2A?displayProperty=fullName> se implementan como propiedades públicas virtuales. Reemplazan las implementaciones de interfaz explícitas correspondientes, <xref:System.Data.Common.DbParameter.System%23Data%23IDbDataParameter%23Precision%2A?displayProperty=fullName> y <xref:System.Data.Common.DbParameter.System%23Data%23IDbDataParameter%23Scale%2A?displayProperty=fullName>.|El cambio solo afecta a los desarrolladores que compilan un proveedor de bases de datos de ADO.NET.|Avanzado|  
  
<a name="MSBuild"></a>   
## Cambios de redestinación de MSBuild  
  
|Característica|Cambio|Impacto|Ámbito|  
|--------------------|------------|-------------|------------|  
|Tarea `ResolveAssemblyReference`|La tarea emite una advertencia, MSB3270, que indica que una referencia o cualquiera de sus dependencias no coincide con la arquitectura de la aplicación. Por ejemplo, esto ocurre si una aplicación compilada con la opción `anycpu` incluye una referencia a x86. Este tipo de escenario podría producir un error de la aplicación en tiempo de ejecución \(en este caso, si la aplicación se implementa como un proceso x64\).|Existen dos áreas de impacto:<br /><br /> -   Una nueva compilación genera advertencias que no aparecieron al compilar la aplicación con una versión anterior de MSBuild. Sin embargo, dado que la advertencia identifica un posible origen de errores en el runtime, se debe investigar y solucionar.<br />-   Si las advertencias se tratan como errores, la aplicación no se compilará.|Secundaria|  
  
## Vea también  
 [Cambios en tiempo de ejecución](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-5-1.md)   
 [Compatibilidad de aplicaciones en 4.5](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5.md)   
 [Compatibilidad de aplicaciones en 4.5.2](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5-2.md)