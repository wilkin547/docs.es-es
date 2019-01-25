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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 454391eb7a5f1821438837c8fb7e5f8bad6b5723
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54651664"
---
# <a name="imetadataassemblyimportfindassembliesbyname-method"></a>IMetaDataAssemblyImport::FindAssembliesByName (Método)
Obtiene una matriz de ensamblados con los valores especificados `szAssemblyName` parámetro, utilizando las reglas estándares empleadas por common language runtime (CLR) para resolver las referencias.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT FindAssembliesByName (  
    [in]  LPCWSTR     szAppBase,   
    [in]  LPCWSTR     szPrivateBin,   
    [in]  LPCWSTR     szAssemblyName,   
    [out] IUnknown    *ppIUnk[],   
    [in]  ULONG       cMax,   
    [out] ULONG       *pcAssemblies  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `szAppBase`  
 [in] El directorio raíz en el que se va a buscar el ensamblado especificado. Si este valor se establece en `null`, `FindAssembliesByName` buscará solo en la caché global de ensamblados para el ensamblado.  
  
 `szPrivateBin`  
 [in] Una lista de los subdirectorios delimitada por punto y coma (por ejemplo, "bin; bin2"), en el directorio raíz, en el que se va a buscar el ensamblado. Además de aquéllos especificados en las reglas de sondeo predeterminado se busca en estos directorios.  
  
 `szAssemblyName`  
 [in] El nombre del ensamblado que se va a buscar. El formato de esta cadena se define en la página de referencia de clase para <xref:System.Reflection.AssemblyName>.  
  
 `ppIUnk`  
 [in] Una matriz de tipo [IUnknown](/cpp/atl/iunknown) en el que se va a colocar el `IMetadataAssemblyImport` punteros de interfaz.  
  
 `cMax`  
 [out] El número máximo de punteros de interfaz que se pueden colocar en `ppIUnk`.  
  
 `pcAssemblies`  
 [out] Devuelve el número de punteros de interfaz. Es decir, el número de punteros de interfaz realmente colocados en `ppIUnk`.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|`S_OK`|`FindAssembliesByName` se devolvió correctamente.|  
|`S_FALSE`|No hay ningún ensamblado.|  
  
## <a name="remarks"></a>Comentarios  
 Asigna un nombre de ensamblado, el `FindAssembliesByName` método encuentra el ensamblado siguiendo las reglas estándar para resolver las referencias de ensamblado. (Para obtener más información, consulte [How the Runtime Locates Assemblies](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).) `FindAssembliesByName` permite al llamador configurar varios aspectos del contexto de resolución de ensamblado, como la ruta de acceso de búsqueda privada y base de aplicación.  
  
 El `FindAssembliesByName` método requiere que se puede inicializar en el proceso para invocar la lógica de resolución de ensamblado CLR. Por lo tanto, debe llamar a [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) (pasando COINITEE_DEFAULT) antes de llamar a `FindAssembliesByName`y, a continuación, siga con una llamada a [CoUninitializeCor](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md).  
  
 `FindAssembliesByName` Devuelve un [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) puntero en el archivo que contiene el manifiesto del ensamblado para el nombre del ensamblado que se pasa. Si el nombre del ensamblado no se especifica completamente (por ejemplo, si no tiene una versión), se podrían devolver varios ensamblados.  
  
 `FindAssembliesByName` se utiliza normalmente mediante un compilador que intenta encontrar un ensamblado que se hace referencia en tiempo de compilación.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Usar como un recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [Cómo el motor en tiempo de ejecución ubica ensamblados](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [IMetaDataAssemblyImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
