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
ms.openlocfilehash: c0f81e3767d4ea3bc336203fbe8c914b4e2bd07b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177800"
---
# <a name="imetadataassemblyimportfindassembliesbyname-method"></a>IMetaDataAssemblyImport::FindAssembliesByName (Método)
Obtiene una matriz de ensamblados `szAssemblyName` con el parámetro especificado, utilizando las reglas estándar empleadas por Common Language Runtime (CLR) para resolver referencias.  
  
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
 [en] El directorio raíz en el que se va a buscar el ensamblado especificado. Si este valor `null`se `FindAssembliesByName` establece en , buscará solo en la caché global de ensamblados para el ensamblado.  
  
 `szPrivateBin`  
 [en] Una lista de subdirectorios delimitados por punto y coma (por ejemplo, "bin;bin2"), en el directorio raíz, en el que buscar el ensamblado. Estos directorios se sondean además de los especificados en las reglas de sondeo predeterminadas.  
  
 `szAssemblyName`  
 [en] El nombre del ensamblado que se ha de buscar. El formato de esta cadena se define <xref:System.Reflection.AssemblyName>en la página de referencia de clase para .  
  
 `ppIUnk`  
 [en] Matriz de tipo [IUnknown](/cpp/atl/iunknown) en `IMetadataAssemblyImport` la que se colocan los punteros de interfaz.  
  
 `cMax`  
 [fuera] El número máximo de punteros de `ppIUnk`interfaz que se pueden colocar en .  
  
 `pcAssemblies`  
 [fuera] El número de punteros de interfaz devueltos. Es decir, el número de punteros de interfaz colocados en `ppIUnk`.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|`S_OK`|`FindAssembliesByName`regresó con éxito.|  
|`S_FALSE`|No hay ensamblados.|  
  
## <a name="remarks"></a>Observaciones  
 Dado un nombre `FindAssembliesByName` de ensamblado, el método busca el ensamblado siguiendo las reglas estándar para resolver referencias de ensamblado. (Para obtener más información, consulte cómo el motor en tiempo de [ejecución localiza ensamblados](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).) `FindAssembliesByName` permite al autor de la llamada configurar varios aspectos del contexto de resolución de ensamblado, como la base de aplicaciones y la ruta de búsqueda privada.  
  
 El `FindAssembliesByName` método requiere que CLR se inicialice en el proceso para invocar la lógica de resolución de ensamblados. Por lo tanto, debe llamar a [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) (pasando COINITEE_DEFAULT) antes de llamar `FindAssembliesByName`y, a continuación, seguir con una llamada a [CoUninitializeCor](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md).  
  
 `FindAssembliesByName`devuelve un [puntero IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) al archivo que contiene el manifiesto del ensamblado para el nombre del ensamblado que se pasa. Si el nombre de ensamblado especificado no se especifica completamente (por ejemplo, si no incluye una versión), es posible que se devuelvan varios ensamblados.  
  
 `FindAssembliesByName`normalmente se usa un compilador que intenta encontrar un ensamblado al que se hace referencia en tiempo de compilación.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** Se utiliza como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Cómo el motor en tiempo de ejecución ubica ensamblados](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [IMetaDataAssemblyImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
