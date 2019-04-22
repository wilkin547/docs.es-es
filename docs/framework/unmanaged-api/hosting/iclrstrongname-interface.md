---
title: ICLRStrongName (Interfaz)
ms.date: 03/30/2017
api_name:
- ICLRStrongName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName
helpviewer_keywords:
- ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 2fac66fd-6b3b-4dbd-8baf-86038bd85526
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: abe967195694dd61b4af18fb4eebbc3caad2ef4f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59205867"
---
# <a name="iclrstrongname-interface"></a>ICLRStrongName (Interfaz)
Proporciona funciones estáticas globales para básicas para firmar los ensamblados con nombres seguros. Todos los `ICLRStrongName` métodos devuelven valores HRESULT de COM estándar.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetHashFromAssemblyFile (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md)|Obtiene un hash del archivo de ensamblado especificado mediante un algoritmo hash concreto.|  
|[GetHashFromAssemblyFileW (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md)|Obtiene un hash del archivo de ensamblado especificado como cadena Unicode mediante un algoritmo hash concreto.|  
|[GetHashFromBlob (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md)|Obtiene un hash del ensamblado en la dirección de memoria especificada mediante un algoritmo hash concreto.|  
|[GetHashFromFile (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)|Genera un hash a partir del contenido del archivo especificado.|  
|[GetHashFromFileW (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)|Genera un hash a partir del contenido del archivo especificado por una cadena Unicode.|  
|[GetHashFromHandle (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md)|Genera un hash a partir del contenido del archivo con el identificador de archivos especificado mediante un algoritmo hash concreto.|  
|[StrongNameCompareAssemblies (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamecompareassemblies-method.md)|Determina si dos ensamblados presentan diferencias solo mediante sus firmas de nombres seguros.|  
|[StrongNameFreeBuffer (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)|Libera la memoria que se asignó con una llamada anterior a un método de nombre seguro como [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md), [StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md), o [StrongNameSignatureGeneration ](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md).|  
|[StrongNameGetBlob (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md)|Llena el búfer especificado con la representación binaria del archivo ejecutable en la dirección especificada.|  
|[StrongNameGetBlobFromImage (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md)|Obtiene una representación binaria de la imagen de ensamblado en la dirección de memoria especificada.|  
|[StrongNameGetPublicKey (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)|Obtiene la clave pública de un par de claves pública y privada.|  
|[StrongNameHashSize (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamehashsize-method.md)|Obtiene el tamaño de búfer necesario para un hash mediante el algoritmo hash especificado.|  
|[StrongNameKeyDelete (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md)|Elimina el contenedor de claves especificado.|  
|[StrongNameKeyGen (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)|Crea un par de claves pública y privada para su uso en nombres seguros.|  
|[StrongNameKeyGenEx (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md)|Genera un par de claves pública y privada con el tamaño de clave especificado para su uso en nombres seguros.|  
|[StrongNameKeyInstall (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md)|Importa un par de claves pública y privada a un contenedor.|  
|[StrongNameSignatureGeneration (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md)|Genera una firma de nombres seguros para el ensamblado especificado.|  
|[StrongNameSignatureGenerationEx (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)|Genera una firma de nombre seguro para el ensamblado especificado en función de las marcas indicadas.|  
|[StrongNameSignatureSize (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturesize-method.md)|Devuelve el tamaño de la firma de nombre seguro.|  
|[StrongNameSignatureVerification (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)|Obtiene un valor que indica si el manifiesto del ensamblado en la ruta de acceso proporcionada contiene una firma de nombre seguro, que se comprueba según las marcas indicadas.|  
|[StrongNameSignatureVerificationEx (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)|Obtiene un valor que indica si el manifiesto del ensamblado en la ruta de acceso proporcionada contiene una firma de nombre seguro.|  
|[StrongNameSignatureVerificationFromImage (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md)|Comprueba si un ensamblado que ya se ha asignado a la memoria es válido para la clave pública asociada.|  
|[StrongNameTokenFromAssembly (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassembly-method.md)|Crea un token de nombre seguro desde el archivo de ensamblado especificado.|  
|[StrongNameTokenFromAssemblyEx (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)|Crea un token de nombre seguro desde el archivo de ensamblado especificado y devuelve la clave pública.|  
|[StrongNameTokenFromPublicKey (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)|Obtiene un token que representa una clave pública.|  
  
## <a name="remarks"></a>Comentarios  
 Puede obtener una instancia de la `ICLRStrongName` mediante una llamada a la [ICLRRuntimeInfo:: GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) utilizando el método `CLSID_CLRStrongName` y `IID_ICLRStrongName` como parámetros.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MetaHost.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Hospedar aplicaciones de WPF](../../../../docs/framework/unmanaged-api/hosting/index.md)
