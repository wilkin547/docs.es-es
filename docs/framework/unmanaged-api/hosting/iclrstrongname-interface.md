---
description: 'Más información acerca de: interfaz ICLRStrongName'
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
ms.openlocfilehash: 5565e864d35e68e714602b291a724a0ad9999a28
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799673"
---
# <a name="iclrstrongname-interface"></a>ICLRStrongName (Interfaz)

Proporciona funciones estáticas globales básicas para firmar ensamblados con nombres seguros. Todos los `ICLRStrongName` métodos devuelven valores HRESULT de com estándar.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método GetHashFromAssemblyFile](iclrstrongname-gethashfromassemblyfile-method.md)|Obtiene un hash del archivo de ensamblado especificado mediante un algoritmo hash concreto.|  
|[Método GetHashFromAssemblyFileW](iclrstrongname-gethashfromassemblyfilew-method.md)|Obtiene un hash del archivo de ensamblado especificado como cadena Unicode mediante un algoritmo hash concreto.|  
|[Método GetHashFromBlob](iclrstrongname-gethashfromblob-method.md)|Obtiene un hash del ensamblado en la dirección de memoria especificada mediante un algoritmo hash concreto.|  
|[Método GetHashFromFile](iclrstrongname-gethashfromfile-method.md)|Genera un hash a partir del contenido del archivo especificado.|  
|[Método GetHashFromFileW](iclrstrongname-gethashfromfilew-method.md)|Genera un hash a partir del contenido del archivo especificado por una cadena Unicode.|  
|[Método GetHashFromHandle](iclrstrongname-gethashfromhandle-method.md)|Genera un hash a partir del contenido del archivo con el identificador de archivos especificado mediante un algoritmo hash concreto.|  
|[Método StrongNameCompareAssemblies](iclrstrongname-strongnamecompareassemblies-method.md)|Determina si dos ensamblados presentan diferencias solo mediante sus firmas de nombres seguros.|  
|[Método StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md)|Libera la memoria que se asignó con una llamada anterior a un método de nombre seguro como [StrongNameGetPublicKey (](iclrstrongname-strongnamegetpublickey-method.md), [StrongNameTokenFromPublicKey (](iclrstrongname-strongnametokenfrompublickey-method.md)o [StrongNameSignatureGeneration (](iclrstrongname-strongnamesignaturegeneration-method.md).|  
|[Método StrongNameGetBlob](iclrstrongname-strongnamegetblob-method.md)|Llena el búfer especificado con la representación binaria del archivo ejecutable en la dirección especificada.|  
|[Método StrongNameGetBlobFromImage](iclrstrongname-strongnamegetblobfromimage-method.md)|Obtiene una representación binaria de la imagen de ensamblado en la dirección de memoria especificada.|  
|[Método StrongNameGetPublicKey](iclrstrongname-strongnamegetpublickey-method.md)|Obtiene la clave pública de un par de claves pública y privada.|  
|[Método StrongNameHashSize](iclrstrongname-strongnamehashsize-method.md)|Obtiene el tamaño de búfer necesario para un hash mediante el algoritmo hash especificado.|  
|[Método StrongNameKeyDelete](iclrstrongname-strongnamekeydelete-method.md)|Elimina el contenedor de claves especificado.|  
|[Método StrongNameKeyGen](iclrstrongname-strongnamekeygen-method.md)|Crea un par de claves pública y privada para su uso en nombres seguros.|  
|[Método StrongNameKeyGenEx](iclrstrongname-strongnamekeygenex-method.md)|Genera un par de claves pública y privada con el tamaño de clave especificado para su uso en nombres seguros.|  
|[Método StrongNameKeyInstall](iclrstrongname-strongnamekeyinstall-method.md)|Importa un par de claves pública y privada a un contenedor.|  
|[Método StrongNameSignatureGeneration](iclrstrongname-strongnamesignaturegeneration-method.md)|Genera una firma de nombres seguros para el ensamblado especificado.|  
|[Método StrongNameSignatureGenerationEx](iclrstrongname-strongnamesignaturegenerationex-method.md)|Genera una firma de nombre seguro para el ensamblado especificado en función de las marcas indicadas.|  
|[Método StrongNameSignatureSize](iclrstrongname-strongnamesignaturesize-method.md)|Devuelve el tamaño de la firma de nombre seguro.|  
|[Método StrongNameSignatureVerification](iclrstrongname-strongnamesignatureverification-method.md)|Obtiene un valor que indica si el manifiesto del ensamblado en la ruta de acceso proporcionada contiene una firma de nombre seguro, que se comprueba según las marcas indicadas.|  
|[Método StrongNameSignatureVerificationEx](iclrstrongname-strongnamesignatureverificationex-method.md)|Obtiene un valor que indica si el manifiesto del ensamblado en la ruta de acceso proporcionada contiene una firma de nombre seguro.|  
|[Método StrongNameSignatureVerificationFromImage](iclrstrongname-strongnamesignatureverificationfromimage-method.md)|Comprueba si un ensamblado que ya se ha asignado a la memoria es válido para la clave pública asociada.|  
|[Método StrongNameTokenFromAssembly](iclrstrongname-strongnametokenfromassembly-method.md)|Crea un token de nombre seguro desde el archivo de ensamblado especificado.|  
|[Método StrongNameTokenFromAssemblyEx](iclrstrongname-strongnametokenfromassemblyex-method.md)|Crea un token de nombre seguro desde el archivo de ensamblado especificado y devuelve la clave pública.|  
|[Método StrongNameTokenFromPublicKey](iclrstrongname-strongnametokenfrompublickey-method.md)|Obtiene un token que representa una clave pública.|  
  
## <a name="remarks"></a>Observaciones  

 Puede obtener una instancia de llamando al `ICLRStrongName` método [ICLRRuntimeInfo:: GetInterface](iclrruntimeinfo-getinterface-method.md) usando `CLSID_CLRStrongName` y `IID_ICLRStrongName` como parámetros.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Metahost. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de hospedaje](hosting-interfaces.md)
- [Hospedar aplicaciones de WPF](index.md)
