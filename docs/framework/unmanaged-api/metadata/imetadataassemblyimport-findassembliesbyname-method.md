---
title: IMetaDataAssemblyImport::FindAssembliesByName (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.FindAssembliesByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::FindAssembliesByName
helpviewer_keywords:
- FindAssembliesByName method [.NET Framework metadata]
- IMetaDataAssemblyImport::FindAssembliesByName method [.NET Framework metadata]
ms.assetid: 4db97cf9-e4c1-4233-8efa-cbdc0e14a8e4
topic_type:
- apiref
ms.openlocfilehash: d2693a94f02214df6d7265b26e3d70d91adcf8a7
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503840"
---
# <a name="imetadataassemblyimportfindassembliesbyname-method"></a>IMetaDataAssemblyImport::FindAssembliesByName (Método)
Obtiene una matriz de ensamblados con el `szAssemblyName` parámetro especificado, utilizando las reglas estándar empleadas por el Common Language Runtime (CLR) para resolver las referencias.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT FindAssembliesByName (  
    [in]  LPCWSTR     szAppBase,
    [in]  LPCWSTR     szPrivateBin,
    [in]  LPCWSTR     szAssemblyName,
    [out] IUnknown    *ppIUnk[],
    [in]  ULONG       cMax,
    [out] ULONG       *pcAssemblies  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `szAppBase`  
 de Directorio raíz en el que se va a buscar el ensamblado especificado. Si este valor se establece en `null` , `FindAssembliesByName` solo buscará en la caché global de ensamblados el ensamblado.  
  
 `szPrivateBin`  
 de Lista de subdirectorios delimitados por punto y coma (por ejemplo, "bin; bin2"), en el directorio raíz, en el que se va a buscar el ensamblado. Estos directorios se sondean además de los especificados en las reglas de búsqueda predeterminadas.  
  
 `szAssemblyName`  
 de Nombre del ensamblado que se va a buscar. El formato de esta cadena se define en la página de referencia de clase de <xref:System.Reflection.AssemblyName> .  
  
 `ppIUnk`  
 de Matriz de tipo [IUnknown](/cpp/atl/iunknown) en la que se colocan los `IMetadataAssemblyImport` punteros de interfaz.  
  
 `cMax`  
 enuncia Número máximo de punteros de interfaz que se pueden colocar en `ppIUnk` .  
  
 `pcAssemblies`  
 enuncia Número de punteros de interfaz devueltos. Es decir, el número de punteros de interfaz que se colocan realmente en `ppIUnk` .  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Description|  
|-------------|-----------------|  
|`S_OK`|`FindAssembliesByName`se devolvió correctamente.|  
|`S_FALSE`|No hay ningún ensamblado.|  
  
## <a name="remarks"></a>Comentarios  
 Dado un nombre de ensamblado, el `FindAssembliesByName` método busca el ensamblado siguiendo las reglas estándar para resolver las referencias de ensamblado. (Para obtener más información, vea [cómo el motor en tiempo de ejecución ubica ensamblados](../../deployment/how-the-runtime-locates-assemblies.md)). `FindAssembliesByName`permite al llamador configurar varios aspectos del contexto de la resolución de ensamblado, como la base de la aplicación y la ruta de acceso de búsqueda privada.  
  
 El `FindAssembliesByName` método requiere que se inicialice el CLR en el proceso para invocar la lógica de resolución de ensamblados. Por lo tanto, debe llamar a [coinicializar](../hosting/coinitializeee-function.md) (pasando COINITEE_DEFAULT) antes de llamar a `FindAssembliesByName` y después seguir con una llamada a [couninitializecor (](../hosting/couninitializecor-function.md).  
  
 `FindAssembliesByName`Devuelve un puntero [IMetaDataImport](imetadataimport-interface.md) al archivo que contiene el manifiesto del ensamblado para el nombre de ensamblado que se pasa. Si el nombre de ensamblado especificado no se especifica completamente (por ejemplo, si no incluye una versión), es posible que se devuelvan varios ensamblados.  
  
 `FindAssembliesByName`suele ser utilizado por un compilador que intenta buscar un ensamblado al que se hace referencia en tiempo de compilación.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se utiliza como recurso en MsCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Cómo el motor en tiempo de ejecución ubica ensamblados](../../deployment/how-the-runtime-locates-assemblies.md)
- [IMetaDataAssemblyImport (Interfaz)](imetadataassemblyimport-interface.md)
