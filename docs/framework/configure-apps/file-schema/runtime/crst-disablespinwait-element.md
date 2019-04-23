---
title: elemento < Crst_DisableSpinWait >
ms.date: 04/18/2019
f1_keywords:
- Crst_DisableSpinWait
helpviewer_keywords:
- Crst_DisableSpinWait element
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6cde26250db0b3d11c51a18b7ebd378953ae0958
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2019
ms.locfileid: "59981259"
---
# <a name="crstdisablespinwait-element"></a>\<Crst_DisableSpinWait > elemento

Especifica si se deshabilita el ciclo de espera para una sección crítica cuando contenidos. \ 
  
 \<configuration>  
\<runtime>  
\<Crst_DisableSpinWait>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<Crst_DisableSpinWait enabled="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos

En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|**enabled**|Especifica si el ciclo de espera para las secciones críticas está habilitada cuando están contenidos.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|1|Ciclo de espera está habilitado.|  
|0|Ciclo de espera está deshabilitado. Este es el valor predeterminado|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información sobre las diversas opciones de configuración en tiempo de ejecución.|  
  
## <a name="example"></a>Ejemplo  

El siguiente ejemplo se deshabilita en espera flechas en las secciones críticas cuando contenidos.  
  
```xml  
<configuration>  
   <runtime>  
      <Crst_DisableSpinWait enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también

- [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)
