---
title: <useLegacyJit> (Elemento)
ms.date: 04/26/2017
ms.assetid: c2cf97f0-9262-4f1f-a754-5568b51110ad
ms.openlocfilehash: a126b8c0050a8d1fd96a3d090f9b018a9faa07a7
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "73968851"
---
# <a name="uselegacyjit-element"></a>\<useLegacyJit> (Elemento)

Determina si Common Language Runtime usa el compilador JIT de 64 bits heredado para la compilación Just-In-Time.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<useLegacyJit>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml
<useLegacyJit enabled=0|1 />
```

El nombre del elemento `useLegacyJit` distingue mayúsculas de minúsculas.
  
## <a name="attributes-and-elements"></a>Atributos y elementos

En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
| Atributo | Descripción                                                                                   |  
| --------- | --------------------------------------------------------------------------------------------- |  
| `enabled` | Atributo necesario.<br><br>Especifica si el motor en tiempo de ejecución utiliza el compilador JIT de 64 bits heredado. |  
  
### <a name="enabled-attribute"></a>atributo Enabled  
  
| Value | Descripción                                                                                                         |  
| ----- | ------------------------------------------------------------------------------------------------------------------- |  
| 0     | En el Common Language Runtime se usa el nuevo compilador JIT de 64 bits incluido en el .NET Framework 4,6 y versiones posteriores. |  
| 1     | En el Common Language Runtime se usa el compilador JIT de 64 bits anterior.                                                     |  
  
### <a name="child-elements"></a>Elementos secundarios

None
  
### <a name="parent-elements"></a>Elementos primarios  
  
| Elemento         | Descripción                                                                                                       |  
| --------------- | ----------------------------------------------------------------------------------------------------------------- |  
| `configuration` | Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework. |  
| `runtime`       | Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.                                                        |  
  
## <a name="remarks"></a>Comentarios  

A partir de la .NET Framework 4,6, el Common Language Runtime utiliza de forma predeterminada un nuevo compilador de 64 bits para la compilación Just-in-Time (JIT). En algunos casos, esto puede dar lugar a una diferencia en el comportamiento del código de la aplicación que compiló JIT por la versión anterior del compilador JIT de 64 bits. Al establecer el `enabled` atributo del `<useLegacyJit>` elemento en `1` , puede deshabilitar el nuevo compilador JIT de 64 bits y compilar la aplicación con el compilador JIT de 64 bits heredado.  
  
> [!NOTE]
> El `<useLegacyJit>` elemento afecta solo a la compilación JIT de 64 bits. La compilación con el compilador JIT de 32 bits no se ve afectada.  
  
En lugar de utilizar un valor de archivo de configuración, puede habilitar el compilador JIT de 64 bits heredado de otras dos maneras:  
  
- Establecer una variable de entorno

  Establezca la `COMPLUS_useLegacyJit` variable de entorno en `0` (use el nuevo compilador jit de 64 bits) o `1` (use el anterior compilador JIT de 64 bits):
  
  ```env  
  COMPLUS_useLegacyJit=0|1  
  ```  
  
  La variable de entorno tiene *ámbito global*, lo que significa que afecta a todas las aplicaciones que se ejecutan en la máquina. Si se establece, puede reemplazarse por la configuración del archivo de configuración de la aplicación. El nombre de la variable de entorno no distingue mayúsculas de minúsculas.
  
- Agregar una clave del registro

  Puede habilitar el compilador JIT de 64 bits heredado agregando un `REG_DWORD` valor a `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` la `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` clave o del registro. El valor se denomina `useLegacyJit` . Si el valor es 0, se utiliza el nuevo compilador. Si el valor es 1, el compilador JIT de 64 bits heredado está habilitado. El nombre del valor de registro no distingue mayúsculas de minúsculas.
  
  Agregar el valor a la `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` clave afecta a todas las aplicaciones que se ejecutan en la máquina. Agregar el valor a la `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` clave afecta a todas las aplicaciones ejecutadas por el usuario actual. Si un equipo se configura con varias cuentas de usuario, solo se verán afectadas las aplicaciones ejecutadas por el usuario actual, a menos que el valor se agregue también a las claves del registro para otros usuarios. Al agregar el `<useLegacyJit>` elemento a un archivo de configuración, se invalida la configuración del registro, si está presente.  
  
## <a name="example"></a>Ejemplo  

El siguiente archivo de configuración deshabilita la compilación con el nuevo compilador JIT de 64 bits y, en su lugar, utiliza el compilador JIT de 64 bits heredado.  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
  <runtime>  
    <useLegacyJit enabled="1" />  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Consulte también

- [\<runtime>Element](runtime-element.md)
- [\<configuration>Element](../configuration-element.md)
- [Mitigación: Nuevo compilador JIT de 64 bits](../../../migration-guide/mitigation-new-64-bit-jit-compiler.md)
