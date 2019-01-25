---
title: '&lt;useLegacyJit&gt; Element'
ms.date: 04/26/2017
ms.assetid: c2cf97f0-9262-4f1f-a754-5568b51110ad
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ecf4d805feeb27a7c3fa08d2ab6dd05b6fff693a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54648185"
---
# <a name="ltuselegacyjitgt-element"></a>&lt;useLegacyJit&gt; Element

Determina si Common Language Runtime usa el compilador JIT de 64 bits heredado para la compilación Just-In-Time.  
  
\<configuration>  
\<runtime>  
\<useLegacyJit>
  
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
| `enabled` | Atributo necesario.<br><br>Especifica si el runtime usa el compilador JIT de 64 bits heredado. |  
  
### <a name="enabled-attribute"></a>atributo enabled  
  
| Valor | Descripción                                                                                                         |  
| ----- | ------------------------------------------------------------------------------------------------------------------- |  
| 0     | Common language runtime usa el nuevo compilador JIT de 64 bits incluido en .NET Framework 4.6 y versiones posteriores. |  
| 1     | Common language runtime usa el compilador JIT de 64 bits antiguo.                                                     |  
  
### <a name="child-elements"></a>Elementos secundarios

Ninguna
  
### <a name="parent-elements"></a>Elementos primarios  
  
| Elemento         | Descripción                                                                                                       |  
| --------------- | ----------------------------------------------------------------------------------------------------------------- |  
| `configuration` | Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework. |  
| `runtime`       | Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.                                                        |  
  
## <a name="remarks"></a>Comentarios  

A partir de la versión 4.6 de .NET Framework, common language runtime usa un nuevo compilador de 64 bits para la compilación Just In Time (JIT) de forma predeterminada. En algunos casos, esto puede producir una diferencia de comportamiento del código de aplicación que se ha compilado JIT por la versión anterior del compilador JIT de 64 bits. Estableciendo el `enabled` atributo de la `<useLegacyJit>` elemento `1`, puede deshabilitar el nuevo compilador JIT de 64 bits y en su lugar, compile la aplicación mediante el compilador JIT de 64 bits heredado.  
  
> [!NOTE]
> El `<useLegacyJit>` elemento afecta a la compilación de JIT de 64 bits sólo. Compilación con el compilador JIT de 32 bits no se ve afectado.  
  
En lugar de usar un archivo de configuración, puede habilitar el compilador JIT de 64 bits heredado de dos formas:  
  
- Establecer una variable de entorno

  Establecer el `COMPLUS_useLegacyJit` una variable de entorno `0` (usar el nuevo compilador JIT de 64 bits) o `1` (usar el compilador JIT de 64 bits antiguo):
  
  ```  
  COMPLUS_useLegacyJit=0|1  
  ```  
  
  La variable de entorno tiene *ámbito global*, lo que significa que afecta a todas las aplicaciones que se ejecutan en el equipo. Si se establece, se puede reemplazarse por el archivo de configuración de aplicación. El nombre de variable de entorno no distingue mayúsculas de minúsculas.
  
- Agregar una clave del registro

  Puede habilitar el compilador JIT de 64 bits heredado mediante la adición de un `REG_DWORD` valor como el `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` o `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` clave en el registro. El valor se denomina `useLegacyJit`. Si el valor es 0, se utiliza el nuevo compilador. Si el valor es 1, se habilita el compilador JIT de 64 bits heredado. El nombre del valor del registro no distingue mayúsculas de minúsculas.
  
  Adición del valor para el `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` clave afecta a todas las aplicaciones que se ejecutan en el equipo. Adición del valor para el `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` clave afecta a todas las aplicaciones que ejecuta el usuario actual. Si un equipo está configurado con varias cuentas de usuario, solo las aplicaciones que ejecuta el usuario actual se ven afectadas, a menos que el valor se agrega a las claves del registro para que así otros usuarios. Agregar el `<useLegacyJit>` elemento a un archivo de configuración reemplaza la configuración del registro, si están presentes.  
  
## <a name="example"></a>Ejemplo  

El archivo de configuración siguiente deshabilita la compilación con el nuevo compilador JIT de 64 bits y usa en su lugar, el compilador JIT de 64 bits heredado.  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
  <runtime>  
    <useLegacyJit enabled="1" />  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también

- [\<en tiempo de ejecución > elemento](../../../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)
- [Elemento \<configuration>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)
- [Mitigación: Nuevo compilador JIT de 64 bits](../../../../../docs/framework/migration-guide/mitigation-new-64-bit-jit-compiler.md)
