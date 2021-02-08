---
description: 'Más información acerca de: <PreferComInsteadOfManagedRemoting> elemento'
title: <PreferComInsteadOfManagedRemoting> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- <PreferComInsteadOfManagedRemoting> element
- PreferComInsteadOfManagedRemoting element
ms.assetid: a279a42a-c415-4e79-88cf-64244ebda613
ms.openlocfilehash: b621af9b584d1ea2623ffe5a44f74b5b7bd520e7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99782278"
---
# <a name="prefercominsteadofmanagedremoting-element"></a>\<PreferComInsteadOfManagedRemoting> (Elemento)

Especifica si el tiempo de ejecución usará la interoperabilidad COM en lugar de la comunicación remota para todas las llamadas en los límites del dominio de aplicación.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<PreferComInsteadOfManagedRemoting>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<PreferComInsteadOfManagedRemoting enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  

 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`enabled`|Atributo necesario.<br /><br /> Indica si el tiempo de ejecución utilizará la interoperabilidad COM en lugar de la comunicación remota entre los límites del dominio de aplicación.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Value|Descripción|  
|-----------|-----------------|  
|`false`|El Runtime usará la comunicación remota en los límites del dominio de aplicación. Este es el valor predeterminado.|  
|`true`|El Runtime usará la interoperabilidad COM en los límites del dominio de aplicación.|  
  
### <a name="child-elements"></a>Elementos secundarios  

 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## <a name="remarks"></a>Observaciones  

 Al establecer el `enabled` atributo en `true` , el tiempo de ejecución se comporta de la siguiente manera:  
  
- El runtime no llama a [IUnknown:: QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)) para una interfaz [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) cuando una interfaz [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) entra en el dominio a través de una interfaz com. En su lugar, crea un contenedor RCW ( [Runtime Callable wrapper](../../../../standard/native-interop/runtime-callable-wrapper.md) ) alrededor del objeto.  
  
- El tiempo de ejecución devuelve E_NOINTERFACE cuando recibe una `QueryInterface` llamada a una interfaz [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) para cualquier contenedor CCW ( [com Callable wrapper](../../../../standard/native-interop/com-callable-wrapper.md) ) que se ha creado en este dominio.  
  
 Estos dos comportamientos garantizan que todas las llamadas a través de interfaces COM entre los objetos administrados a través de los límites del dominio de aplicación utilizan la interoperabilidad com y COM en lugar de la comunicación remota.  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se muestra cómo especificar que el Runtime debe utilizar la interoperabilidad COM en los límites de aislamiento:  
  
```xml  
<configuration>  
  <runtime>  
    <PreferComInsteadOfManagedRemoting enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también

- [Esquema de la configuración de Common Language Runtime](index.md)
- [Esquema de los archivos de configuración](../index.md)
