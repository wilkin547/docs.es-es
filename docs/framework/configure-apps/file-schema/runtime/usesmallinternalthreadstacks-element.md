---
description: 'Más información acerca de: <UseSmallInternalThreadStacks> elemento'
title: <UseSmallInternalThreadStacks> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- UseSmallInternalThreadStacks element
- <UseSmallInternalThreadStacks> element
ms.assetid: 1e3f6ec0-1cac-4e1c-9c81-17d948ae5874
ms.openlocfilehash: eeb253025b32f862926c7315004b1854b8eef928
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99639970"
---
# <a name="usesmallinternalthreadstacks-element"></a>\<UseSmallInternalThreadStacks> (Elemento)

Solicita que el Common Language Runtime (CLR) reduzca el uso de memoria especificando tamaños de pila explícitos al crear determinados subprocesos que utiliza internamente, en lugar de usar el tamaño de pila predeterminado para esos subprocesos.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<UseSmallInternalThreadStacks>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<UseSmallInternalThreadStacks enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  

 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|enabled|Atributo necesario.<br /><br /> Especifica si se debe solicitar que CLR use tamaños de pila explícitos en lugar del tamaño de pila predeterminado cuando crea determinados subprocesos que usa internamente. Los tamaños de pila explícitos son menores que el tamaño de pila predeterminado de 1 MB.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Value|Descripción|  
|-----------|-----------------|  
|true|Solicitar tamaños de pila explícitos.|  
|false|Use el tamaño de pila predeterminado. Este es el valor predeterminado para el .NET Framework 4.|  
  
### <a name="child-elements"></a>Elementos secundarios  

 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## <a name="remarks"></a>Observaciones  

 Este elemento de configuración se usa para solicitar el uso reducido de la memoria virtual en un proceso, porque los tamaños de subproceso explícitos que usa CLR para sus subprocesos internos, si se respeta la solicitud, son menores que el tamaño predeterminado.  
  
> [!IMPORTANT]
> Este elemento de configuración es una solicitud a CLR en lugar de un requisito absoluto. En el .NET Framework 4, la solicitud solo se admite para la arquitectura x86. Este elemento podría omitirse completamente en versiones futuras de CLR o reemplazarse por tamaños de pila explícitos que siempre se usan para los subprocesos internos seleccionados.  
  
 Si se especifica este elemento de configuración, la confiabilidad se usa para reducir el uso de memoria virtual si CLR respeta la solicitud, ya que los tamaños de pila más pequeños podrían provocar desbordamientos de la pila con mayor probabilidad.  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se muestra cómo solicitar que CLR use tamaños de pila explícitos para determinados subprocesos que usa internamente.  
  
```xml  
<configuration>  
   <runtime>  
      <UseSmallInternalThreadStacks enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también

- [Esquema de la configuración de Common Language Runtime](index.md)
- [Esquema de los archivos de configuración](../index.md)
