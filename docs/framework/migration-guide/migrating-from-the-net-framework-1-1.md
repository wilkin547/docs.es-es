---
title: Migración desde .NET Framework 1.1
ms.date: 03/30/2017
helpviewer_keywords:
- .NET Framework 4.5, migrating from 1.1
- .NET Framework 1.1, migrating to .NET Framework 4.5
ms.assetid: 7ead0cb3-3b19-414a-8417-a1c1fa198d9e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dc3c611cf043538e7f069cc1634bd5be5e70dfab
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2018
ms.locfileid: "43392281"
---
# <a name="migrating-from-the-net-framework-11"></a>Migración desde .NET Framework 1.1
[!INCLUDE[win7](../../../includes/win7-md.md)] y las versiones posteriores del sistema operativo Windows no admiten [!INCLUDE[net_v11_long](../../../includes/net-v11-long-md.md)]. En consecuencia, las aplicaciones que tienen como destino [!INCLUDE[net_v11_short](../../../includes/net-v11-short-md.md)] no podrán ejecutarse sin modificaciones en [!INCLUDE[win7](../../../includes/win7-md.md)] o versiones posteriores. En este tema describen los pasos necesarios para ejecutar una aplicación destinada a [!INCLUDE[net_v11_short](../../../includes/net-v11-short-md.md)] en [!INCLUDE[win7](../../../includes/win7-md.md)] y versiones posteriores del sistema operativo Windows. Para obtener más información sobre [!INCLUDE[net_v11_long](../../../includes/net-v11-long-md.md)] y [!INCLUDE[win8](../../../includes/win8-md.md)], vea [Ejecutar aplicaciones .NET Framework 1.1 en Windows 8 y versiones posteriores](../../../docs/framework/install/run-net-framework-1-1-apps.md).  
  
## <a name="retargeting-or-recompiling"></a>Redestinar o recompilar  
 Hay dos formas para conseguir que una aplicación compilada con [!INCLUDE[net_v11_short](../../../includes/net-v11-short-md.md)] se ejecute en [!INCLUDE[win7](../../../includes/win7-md.md)] o un sistema operativo de Windows posterior:  
  
-   Puede redestinar la aplicación para que se ejecute en [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]. Para redestinarla, es necesario agregar un elemento [\<supportedRuntime>](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) al archivo de configuración de la aplicación que permita ejecutarla en [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]. Un archivo de configuración de este tipo tendrá el formato siguiente:  
  
    ```xml  
    <configuration>   
       <startup>  
          <supportedRuntime version="v4.0"/>  
       </startup>  
    </configuration>  
    ```  
  
-   Puede volver a compilar la aplicación con un compilador que tenga como destino [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]. Si originalmente usó Visual Studio 2003 para desarrollar y compilar la solución, puede abrir la solución en [!INCLUDE[vs_dev10_long](../../../includes/vs-dev10-long-md.md)] y usar el cuadro de diálogo **Compatibilidad del proyecto** para convertir la solución y los archivos del proyecto de los formatos utilizados en Visual Studio 2003 a los formatos de Microsoft Build Engine (MSBuild) utilizados en [!INCLUDE[vs_dev10_long](../../../includes/vs-dev10-long-md.md)].  
  
 Independientemente de si prefiere volver a compilar o redestinar la aplicación, deberá determinar si la aplicación se ve afectada por los cambios introducidos en versiones posteriores de .NET Framework. Estos cambios son de dos tipos:  
  
-   Cambios importantes que se produjeron entre [!INCLUDE[net_v11_short](../../../includes/net-v11-short-md.md)] y las versiones posteriores de .NET Framework.  
  
-   Tipos y miembros que se han marcado como desusados u obsoletos entre [!INCLUDE[net_v11_short](../../../includes/net-v11-short-md.md)] y versiones posteriores de .NET Framework.  
  
 Tanto si redestina la aplicación como si vuelve a compilarla, deberá revisar los cambios importantes y los miembros y tipos obsoletos de cada versión de .NET Framework publicada después de [!INCLUDE[net_v11_short](../../../includes/net-v11-short-md.md)].  
  
## <a name="breaking-changes"></a>Cambios importantes  
 Cuando se realiza un cambio importante, en función del cambio concreto, puede haber una solución disponible tanto para las aplicaciones redestinadas como para las que se compilan de nuevo. En algunos casos, puede agregar un elemento secundario al elemento [\<runtime>](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) del archivo de configuración de la aplicación para restaurar el comportamiento anterior. Por ejemplo, el archivo de configuración siguiente restaura el comportamiento de comparación y ordenación de cadenas que se utilizaba en [!INCLUDE[net_v11_short](../../../includes/net-v11-short-md.md)] y puede usarse tanto con una aplicación redestinada como con una aplicación que se ha compilado de nuevo.  
  
```xml  
<configuration>  
   <runtime>  
      <CompatSortNLSVersion enabled="4096"/>  
   </runtime>  
</configuration>  
```  
  
 Sin embargo, en algunos casos, tal vez necesite modificar el código fuente y volver a compilar la aplicación.  
  
 Para valorar el impacto que los posibles cambios importantes podrían tener en su aplicación, debe revisar las siguientes listas de cambios:  
  
-   En[Cambios importantes en .NET Framework 2.0](https://go.microsoft.com/fwlink/?LinkId=125263) se muestran los cambios de [!INCLUDE[net_v20SP1_short](../../../includes/net-v20sp1-short-md.md)] que pueden afectar a una aplicación destinada a [!INCLUDE[net_v11_short](../../../includes/net-v11-short-md.md)].  
  
-   En[Cambios en .NET Framework 3.5 SP1](https://go.microsoft.com/fwlink/?LinkID=186989) se indican los cambios entre [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] y [!INCLUDE[net_v35SP1_short](../../../includes/net-v35sp1-short-md.md)].  
  
-   En[Problemas de migración de .NET Framework 4](../../../docs/framework/migration-guide/net-framework-4-migration-issues.md) se indican los cambios entre [!INCLUDE[net_v35SP1_short](../../../includes/net-v35sp1-short-md.md)] y [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)].  
  
## <a name="obsolete-types-and-members"></a>Tipos y miembros obsoletos  
 El impacto de los tipos y miembros desusados es ligeramente distinto en las aplicaciones redestinadas que en las aplicaciones compiladas de nuevo. El uso de tipos y miembros obsoletos no afectará a la aplicación redestinada a menos que el tipo o miembro obsoleto se haya quitado físicamente del ensamblado. Cuando se vuelve a compilar una aplicación que utiliza tipos y miembros obsoletos, normalmente se produce una advertencia del compilador y no un error del compilador. Sin embargo, en algunos casos, se genera un error del compilador y el código que usa el tipo o miembro obsoleto no se compila correctamente. En este caso, debe volver a escribir el código fuente que llama al tipo o miembro obsoleto antes de volver a compilar la aplicación. Para obtener más información sobre los tipos y miembros obsoletos, vea [Lo obsoleto en la biblioteca de clases de .NET Framework](../../../docs/framework/whats-new/whats-obsolete.md).  
  
 Para valorar el impacto de los tipos y miembros en desuso desde la publicación de [!INCLUDE[net_v20SP1_short](../../../includes/net-v20sp1-short-md.md)], vea [Lo obsoleto en la biblioteca de clases de .NET Framework](../../../docs/framework/whats-new/whats-obsolete.md). Consulte las listas de tipos y miembros obsoletos de [!INCLUDE[net_v20SP1_short](../../../includes/net-v20sp1-short-md.md)], [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] y [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)].
