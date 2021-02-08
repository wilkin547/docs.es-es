---
description: 'Más información acerca de: <Crst_DisableSpinWait elemento>'
title: Elemento <Crst_DisableSpinWait>
ms.date: 04/18/2019
f1_keywords:
- Crst_DisableSpinWait
helpviewer_keywords:
- Crst_DisableSpinWait element
ms.openlocfilehash: fca6fed2dabc3d1319ad030bb13bbb35a561b9aa
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795110"
---
# <a name="crst_disablespinwait-element"></a>\<Crst_DisableSpinWait> (elemento)

Especifica si se va a deshabilitar la espera de giro para una sección crítica cuando esté habilitada.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<Crst_DisableSpinWait>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<Crst_DisableSpinWait enabled="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos

En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|**enabled**|Especifica si está deshabilitada la espera de girar para las secciones críticas cuando están configuradas.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Value|Descripción|  
|-----------|-----------------|  
|1|Deshabilitar el giro en espera cuando no se puede adquirir una sección crítica.|  
|0|No deshabilite la espera de giro cuando no se pueda adquirir una sección crítica. Este es el valor predeterminado.|  
  
### <a name="child-elements"></a>Elementos secundarios  

 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
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
