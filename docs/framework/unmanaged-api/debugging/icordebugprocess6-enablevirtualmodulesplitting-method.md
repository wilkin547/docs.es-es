---
title: Método ICorDebugProcess6::EnableVirtualModuleSplitting
ms.date: 03/30/2017
ms.assetid: e7733bd3-68da-47f9-82ef-477db5f2e32d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b4565deddee2e7714d937bf61574243cc07a4602
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423483"
---
# <a name="icordebugprocess6enablevirtualmodulesplitting-method"></a>Método ICorDebugProcess6::EnableVirtualModuleSplitting
Habilita o deshabilita la división de módulos virtuales.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT EnableVirtualModuleSplitting(  
   BOOL enableSplitting  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `enableSplitting`  
 `true` para habilitar la división de módulos virtuales; `false` para deshabilitarla.  
  
## <a name="remarks"></a>Comentarios  
 Causas de división de módulos virtuales [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) para que reconozca los módulos que se combinaron durante la compilación, procesarán y presentan como un grupo de módulos independientes en lugar de un único módulo de gran tamaño. Esto cambia el comportamiento de diversos [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) métodos que se describen a continuación.  
  
> [!NOTE]
>  Este método solo está disponible con .NET Native.  
  
 Puede llamar a este método y cambiar el valor de `enableSplitting` en cualquier momento. No provoca cambios funcionales con estado en un [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) objeto, aparte de alterar el comportamiento de los métodos enumerados en la [división de módulos virtuales y la API de depuración no administradas](#APIs) sección en el momento en que se les llama. El uso de módulos virtuales hace que el rendimiento disminuya cuando se llama a estos métodos. Además, significativos en la memoria de almacenamiento en caché de los metadatos virtualizados puede necesarios para implementar correctamente la [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) API y estas memorias caché pueden conservarse incluso después de división de módulos virtuales se ha desactivado.  
  
## <a name="terminology"></a>Terminología  
 Los siguientes términos sirven para describir la división de módulos virtuales:  
  
 módulos de contenedor o contenedores  
 Son los módulos agregados.  
  
 submódulos o módulos virtuales  
 Son los módulos incluidos en un contenedor.  
  
 módulos regulares  
 Módulos que no se han combinado en tiempo de compilación. No son ni módulos de contenedor ni submódulos.  
  
 Módulos de contenedor y submódulos se representan mediante objetos de la interfaz de ICorDebugModule. Sin embargo, el comportamiento de la interfaz es ligeramente diferente en cada caso, como el \<x-ref sección > sección se describe.  
  
## <a name="modules-and-assemblies"></a>Módulos y ensamblados  
 En los escenarios donde se combinan ensamblados no se admiten ensamblados con varios módulos, por lo que hay una relación de uno a uno entre un módulo y un ensamblado. Cada objeto ICorDebugModule, independientemente de si representa un módulo contenedor o un submódulo, tiene un objeto ICorDebugAssembly correspondiente. El [ICorDebugModule:: GetAssembly](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getassembly-method.md) método de conversión desde el módulo al ensamblado. Para asignar en el otro sentido, el [ICorDebugAssembly:: EnumerateModules](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-enumeratemodules-method.md) método enumera solo 1 módulo. Dado que ensamblado y módulo conforman un par estrechamente unido en este caso, los términos módulo y ensamblado se han convertido en prácticamente intercambiables.  
  
## <a name="behavioral-differences"></a>Diferencias de comportamiento  
 Los módulos del contenedor tienen los siguientes comportamientos y características:  
  
-   Sus metadatos para todos los submódulos que lo conforman se combinan entre sí.  
  
-   Sus nombres de tipo se pueden alterar.  
  
-   El [ICorDebugModule:: GetName](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getname-method.md) método devuelve la ruta de acceso a un módulo en disco.  
  
-   El [ICorDebugModule:: GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getsize-method.md) método devuelve el tamaño de esa imagen.  
  
-   El método ICorDebugAssembly3.EnumerateContainedAssemblies enumera los submódulos.  
  
-   El método ICorDebugAssembly3.GetContainerAssembly devuelve `S_FALSE`.  
  
 Los submódulos tienen los siguientes comportamientos y características:  
  
-   Tienen un conjunto reducido de metadatos que corresponde únicamente al ensamblado original que se ha combinado.  
  
-   Los nombres de los metadatos no se alteran.  
  
-   Es improbable que los tokens de los metadatos coincidan con los tokens del ensamblado original antes de que combinarse en el proceso de compilación.  
  
-   El [ICorDebugModule:: GetName](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getname-method.md) método devuelve el nombre del ensamblado, no una ruta de acceso de archivo.  
  
-   El [ICorDebugModule:: GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getsize-method.md) método devuelve el tamaño original de la imagen sin combinar.  
  
-   El método ICorDebugModule3.EnumerateContainedAssemblies devuelve `S_FALSE`.  
  
-   El método ICorDebugAssembly3.GetContainerAssembly devuelve el módulo contenedor.  
  
## <a name="interfaces-retrieved-from-modules"></a>Interfaces obtenidas de los módulos  
 Se pueden crear y recuperar diversas interfaces de los módulos. Algunas de ellas son:  
  
-   Un objeto ICorDebugClass, que es devuelto por la [ICorDebugModule:: GetClassFromToken](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getclassfromtoken-method.md) método.  
  
-   Un objeto ICorDebugAssembly, que es devuelto por la [ICorDebugModule:: GetAssembly](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getassembly-method.md) método.  
  
 Estos objetos siempre se almacenan en caché por [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md), que tienen la misma identidad de puntero, independientemente de si se crearon o se consultan desde el módulo contenedor o un subelemento. El submódulo proporciona una vista filtrada de estos objetos en caché, no una memoria caché independiente con sus propias copias.  
  
<a name="APIs"></a>   
## <a name="virtual-module-splitting-and-the-unmanaged-debugging-apis"></a>División de módulos virtuales y API de depuración no administradas  
 En la siguiente tabla se muestra cómo la división de módulos virtuales afecta al comportamiento de otros métodos en una API de depuración no administrada.  
  
|Método|`enableSplitting` = `true`|`enableSplitting` = `false`|  
|------------|---------------------------------|----------------------------------|  
|[ICorDebugFunction:: GetModule](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getmodule-method.md)|Devuelve el submódulo en el que esta función se definió originalmente.|Devuelve el módulo contenedor con el que esta función se combinó.|  
|[ICorDebugClass:: GetModule](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getmodule-method.md)|Devuelve el submódulo en el que esta clase se definió originalmente.|Devuelve el módulo contenedor con el que esta clase se combinó.|  
|ICorDebugModuleDebugEvent::GetModule|Devuelve el módulo contenedor que se cargó. Los submódulos no tienen eventos load, independientemente de esta configuración.|Devuelve el módulo contenedor que se cargó.|  
|[ICorDebugAppDomain:: EnumerateAssemblies](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumerateassemblies-method.md)|Devuelve una lista de los subensamblados y ensamblados regulares; no se incluyen ensamblados de contenedor. **Nota:** si falta símbolos en algún ensamblado de contenedor, se enumerará ninguno de sus Subensamblados. Si faltan símbolos en algún ensamblado regular, puede que se enumere o no.|Devuelve una lista de ensamblados de contenedor y ensamblados regulares; no se incluyen subensamblados. **Nota:** si falta símbolos en algún ensamblado regular, puede o no se puede enumerar.|  
|[ICorDebugCode:: GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md) (cuando se hace referencia a código IL solo)|Devuelve el código IL que sería válido en una imagen de ensamblado antes de la fusión mediante combinación. En concreto, cualquier token de metadatos en línea será correctamente un token TypeRef o MemberRef cuando los tipos a los que se hace referencia no están definidos en el módulo virtual que contiene el IL. Pueden buscar estos tokens TypeRef o MemberRef en el [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) objeto para el objeto ICorDebugModule virtual correspondiente.|Devuelve el IL de la imagen de ensamblado posterior a la fusión mediante combinación.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorDebugProcess6 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)  
 [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
