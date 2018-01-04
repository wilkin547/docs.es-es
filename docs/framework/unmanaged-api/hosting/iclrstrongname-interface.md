---
title: ICLRStrongName (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName
helpviewer_keywords: ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 2fac66fd-6b3b-4dbd-8baf-86038bd85526
topic_type: apiref
caps.latest.revision: "20"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9b8859cf507fb81f07b85b055380ba86aae471b5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongname-interface"></a>ICLRStrongName (Interfaz)
Proporciona funciones estáticas globales para básicas para firmar los ensamblados con nombres seguros. Todos los `ICLRStrongName` métodos devuelven resultados HRESULT COM estándar.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetHashFromAssemblyFile (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md)|Obtiene un valor hash del archivo de ensamblado especificado, utilizando el algoritmo hash especificado.|  
|[GetHashFromAssemblyFileW (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md)|Obtiene un valor hash del archivo de ensamblado especificado como una cadena Unicode, mediante el algoritmo hash especificado.|  
|[GetHashFromBlob (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md)|Obtiene un valor hash del ensamblado en la dirección de memoria especificada, utilizando el algoritmo hash especificado.|  
|[GetHashFromFile (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)|Genera un hash sobre el contenido del archivo especificado.|  
|[GetHashFromFileW (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)|Genera un hash sobre el contenido del archivo especificado por una cadena Unicode.|  
|[GetHashFromHandle (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md)|Genera un hash sobre el contenido del archivo con el identificador de archivo especificado, utilizando el algoritmo hash especificado.|  
|[StrongNameCompareAssemblies (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamecompareassemblies-method.md)|Determina si dos ensamblados difieren solo en sus firmas de nombre seguro.|  
|[StrongNameFreeBuffer (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)|Libera la memoria que se asignó con una llamada anterior a un método de nombre seguro como [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md), [StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md), o [StrongNameSignatureGeneration ](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md).|  
|[StrongNameGetBlob (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md)|Llena el búfer especificado con la representación binaria del archivo ejecutable en la dirección especificada.|  
|[StrongNameGetBlobFromImage (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md)|Obtiene una representación binaria de la imagen de ensamblado en la dirección de memoria especificada.|  
|[StrongNameGetPublicKey (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)|Obtiene la clave pública de un par de claves pública y privada.|  
|[StrongNameHashSize (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamehashsize-method.md)|Obtiene el tamaño de búfer requerido para un hash mediante el algoritmo hash especificado.|  
|[StrongNameKeyDelete (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md)|Elimina el contenedor de claves especificado.|  
|[StrongNameKeyGen (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)|Crea un nuevo par de claves pública y privada para su uso de nombre seguro.|  
|[StrongNameKeyGenEx (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md)|Genera un nuevo par de claves pública/privada con el tamaño de clave especificado para su uso de nombre seguro.|  
|[StrongNameKeyInstall (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md)|Importa un par de claves pública/privada en un contenedor.|  
|[StrongNameSignatureGeneration (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md)|Genera una firma de nombre seguro para el ensamblado especificado.|  
|[StrongNameSignatureGenerationEx (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)|Genera una firma de nombre seguro para el ensamblado especificado, en función de las marcas especificadas.|  
|[StrongNameSignatureSize (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturesize-method.md)|Devuelve el tamaño de la firma de nombre seguro.|  
|[StrongNameSignatureVerification (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)|Obtiene un valor que indica si el manifiesto del ensamblado en la ruta de acceso proporcionada contiene una firma de nombre seguro, que se comprueba según los marcadores especificados.|  
|[StrongNameSignatureVerificationEx (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)|Obtiene un valor que indica si el manifiesto del ensamblado en la ruta de acceso proporcionada contiene una firma de nombre seguro.|  
|[StrongNameSignatureVerificationFromImage (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md)|Comprueba que un ensamblado que ya se ha asignado a la memoria es válido para la clave pública asociada.|  
|[StrongNameTokenFromAssembly (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassembly-method.md)|Crea un token de nombre seguro del archivo de ensamblado especificado.|  
|[StrongNameTokenFromAssemblyEx (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)|Crea un token de nombre seguro del archivo de ensamblado especificado y devuelve la clave pública.|  
|[StrongNameTokenFromPublicKey (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)|Obtiene un token que representa una clave pública.|  
  
## <a name="remarks"></a>Comentarios  
 Puede obtener una instancia de la `ICLRStrongName` mediante una llamada a la [ICLRRuntimeInfo:: GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) método mediante `CLSID_CLRStrongName` y `IID_ICLRStrongName` como parámetros.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MetaHost.h  
  
 **Biblioteca:** incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [Hospedar aplicaciones de WPF](../../../../docs/framework/unmanaged-api/hosting/index.md)
