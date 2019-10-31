---
title: <developmentMode> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/developmentMode
- http://schemas.microsoft.com/.NetConfiguration/v2.0#developmentMode
helpviewer_keywords:
- developmentMode element
- container tags, <developmentMode> element
- <developmentMode> element
ms.assetid: 60e79a8c-415a-497d-be29-b9d0fd9bdee3
ms.openlocfilehash: 4a062da31740edb8f0c7a4f4db8b09800c687587
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73117634"
---
# <a name="developmentmode-element"></a>\<elemento > developmentMode
Especifica si el runtime busca ensamblados en los directorios especificados por la variable de entorno DEVPATH.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<en tiempo de ejecución >** ](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<developmentMode >**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<developmentMode developerInstallation="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|**developerInstallation**|Especifica si el runtime busca ensamblados en los directorios especificados por la variable de entorno DEVPATH.|  
  
## <a name="developerinstallation-attribute"></a>Atributo developerInstallation  
  
|Valor|Descripción|  
|-----------|-----------------|  
|**true**|Busca los ensamblados en los directorios especificados por la variable de entorno DEVPATH.|  
|**false**|No busca ensamblados en los directorios especificados por la variable de entorno DEVPATH. Este es el valor predeterminado|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## <a name="remarks"></a>Comentarios  
 Use esta configuración solo en tiempo de desarrollo. El motor en tiempo de ejecución no comprueba las versiones de los ensamblados con nombre seguro que se encuentran en la DEVPATH. Simplemente usa el primer ensamblado que encuentra.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo hacer que el tiempo de ejecución busque ensamblados en los directorios especificados por la variable de entorno DEVPATH.  
  
```xml  
<configuration>  
   <runtime>  
      <developmentMode developerInstallation="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también

- [Esquema de la configuración de Common Language Runtime](index.md)
- [Esquema de los archivos de configuración](../index.md)
- [Cómo: Buscar ensamblados mediante DEVPATH](../../how-to-locate-assemblies-by-using-devpath.md)
