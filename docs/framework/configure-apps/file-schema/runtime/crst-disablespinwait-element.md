---
title: < elemento > Crst_DisableSpinWait
ms.date: 04/18/2019
f1_keywords:
- Crst_DisableSpinWait
helpviewer_keywords:
- Crst_DisableSpinWait element
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a52dd671f1fbf6fda5bdc92c0935784181eb4b03
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663838"
---
# <a name="crst_disablespinwait-element"></a>\<Crst_DisableSpinWait >, elemento

Especifica si se va a deshabilitar la espera de giro para una sección crítica cuando esté habilitada.  
  
 \<configuration>  
\<> en tiempo de ejecución  
\<Crst_DisableSpinWait>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<Crst_DisableSpinWait enabled="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos

En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|DESCRIPCIÓN|  
|---------------|-----------------|  
|**enabled**|Especifica si está deshabilitada la espera de girar para las secciones críticas cuando están configuradas.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Valor|DESCRIPCIÓN|  
|-----------|-----------------|  
|1|Deshabilitar el giro en espera cuando no se puede adquirir una sección crítica.|  
|0|No deshabilite la espera de giro cuando no se pueda adquirir una sección crítica. Este es el valor predeterminado.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información acerca de diversas opciones de configuración en tiempo de ejecución.|  
  
## <a name="example"></a>Ejemplo  

En el ejemplo siguiente se deshabilita la espera de giro en las secciones críticas cuando está disponible.  
  
```xml  
<configuration>  
   <runtime>  
      <Crst_DisableSpinWait enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también

- [Esquema de la configuración de Common Language Runtime](index.md)
- [Esquema de los archivos de configuración](../index.md)
