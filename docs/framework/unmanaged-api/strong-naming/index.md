---
title: Nombres seguros (Referencia de la API no administrada)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- strong naming [.NET Framework], using the unmanaged API
- native API reference [.NET Framework], strong naming
- unmanaged API reference [.NET Framework], strong naming
ms.assetid: 428c68b6-a7b4-44be-b280-75905f46612c
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ce89e27089ea2f0c918d0fe37c4eea141698f9be
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="strong-naming-unmanaged-api-reference"></a>Nombres seguros (Referencia de la API no administrada)
La API de nombres seguros permite a un cliente administrar la firma de ensamblados con nombre seguro.  
  
 Al firmar un ensamblado con un nombre seguro, se agrega un cifrado mediante clave pública al archivo que contiene el manifiesto del ensamblado. Firmar con nombres seguros ayuda a comprobar la exclusividad del nombre, impide la simulación de nombres y no proporciona una identidad única a los llamadores cuando se resuelve una referencia. Sin embargo, ningún nivel de confianza está asociado con un nombre seguro.  
  
## <a name="in-this-section"></a>En esta sección  
 [Las funciones estáticas globales de nombres seguros](http://msdn.microsoft.com/library/efa715df-e8cc-48f2-9ec4-26586f0dc8d0)  
 Describe las funciones estáticas globales no administradas que utiliza la API de nombres seguros.  
  
> [!NOTE]
>  Todas estas funciones han quedado en desuso a partir de la [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]. Para alternativas sugeridas, consulte el [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md) interfaz.  
  
 [GetHashFromAssemblyFile (Función)](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromassemblyfile-function.md)  
 Obtiene un valor hash del archivo de ensamblado especificado, utilizando el algoritmo hash especificado. En desuso a partir de la [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [GetHashFromAssemblyFileW (Función)](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromassemblyfilew-function.md)  
 Obtiene un valor hash del archivo de ensamblado especificado como una cadena Unicode, mediante el algoritmo hash especificado. En desuso a partir de la [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [GetHashFromBlob (Función)](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromblob-function.md)  
 Obtiene un valor hash del ensamblado en la dirección de memoria especificada, utilizando el algoritmo hash especificado. En desuso a partir de la [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [GetHashFromFile (Función)](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfile-function.md)  
 Genera un hash sobre el contenido del archivo especificado.  En desuso a partir de la [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [GetHashFromFileW (Función)](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfilew-function.md)  
 Genera un hash sobre el contenido del archivo especificado por una cadena Unicode. En desuso a partir de la [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [GetHashFromHandle (Función)](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromhandle-function.md)  
 Genera un hash sobre el contenido del archivo con el identificador de archivo especificado, utilizando el algoritmo hash especificado.  En desuso a partir de la [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameCompareAssemblies (Función)](../../../../docs/framework/unmanaged-api/strong-naming/strongnamecompareassemblies-function.md)  
 Determina si dos ensamblados difieren solo en sus firmas de nombre seguro. En desuso a partir de la [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameErrorInfo (Función)](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md)  
 Obtiene el último código de error que se genera mediante una de las funciones de nombre seguro.  
  
 [StrongNameFreeBuffer (Función)](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md)  
 Libera la memoria que se asignó con una llamada anterior a una función de nombre seguro como [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfrompublickey-function.md), o [StrongNameSignatureGeneration ](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md).   En desuso a partir de la [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameGetBlob (Función)](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetblob-function.md)  
 Llena el búfer especificado con la representación binaria del archivo ejecutable en la dirección especificada. En desuso a partir de la [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameGetBlobFromImage (Función)](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetblobfromimage-function.md)  
 Obtiene una representación binaria de la imagen de ensamblado en la dirección de memoria especificada. En desuso a partir de la [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameGetPublicKey (Función)](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md)  
 Obtiene la clave pública de un par de claves pública y privada. En desuso a partir de la [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameHashSize (Función)](../../../../docs/framework/unmanaged-api/strong-naming/strongnamehashsize-function.md)  
 Obtiene el tamaño de búfer requerido para un hash mediante el algoritmo hash especificado.  En desuso a partir de la [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameKeyDelete (Función)](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeydelete-function.md)  
 Elimina el contenedor de claves especificado. En desuso a partir de la [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameKeyGen (Función)](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeygen-function.md)  
 Crea un nuevo par de claves pública y privada para su uso de nombre seguro.  En desuso a partir de la [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameKeyGenEx (Función)](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeygenex-function.md)  
 Genera un nuevo par de claves pública/privada con el tamaño de clave especificado para su uso de nombre seguro. En desuso a partir de la [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameKeyInstall (Función)](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeyinstall-function.md)  
 Importa un par de claves pública/privada en un contenedor.  En desuso a partir de la [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameSignatureGeneration (Función)](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md)  
 Genera una firma de nombre seguro para el ensamblado especificado.   En desuso a partir de la [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameSignatureGenerationEx (Función)](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegenerationex-function.md)  
 Genera una firma de nombre seguro para el ensamblado especificado, en función de las marcas especificadas.    En desuso a partir de la [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameSignatureSize (Función)](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturesize-function.md)  
 Devuelve el tamaño de la firma de nombre seguro. En desuso a partir de la [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameSignatureVerification (Función)](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverification-function.md)  
 Obtiene un valor que indica si el manifiesto del ensamblado en la ruta de acceso proporcionada contiene una firma de nombre seguro, que se comprueba según los marcadores especificados. En desuso a partir de la [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameSignatureVerificationEx (Función)](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverificationex-function.md)  
 Obtiene un valor que indica si el manifiesto del ensamblado en la ruta de acceso proporcionada contiene una firma de nombre seguro.  En desuso a partir de la [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameSignatureVerificationFromImage (Función)](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverificationfromimage-function.md)  
 Comprueba que un ensamblado que ya se ha asignado a la memoria es válido para la clave pública asociada. En desuso a partir de la [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameTokenFromAssembly (Función)](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassembly-function.md)  
 Crea un token de nombre seguro del archivo de ensamblado especificado.  En desuso a partir de la [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameTokenFromAssemblyEx (Función)](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassemblyex-function.md)  
 Crea un token de nombre seguro del archivo de ensamblado especificado y devuelve la clave pública. En desuso a partir de la [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameTokenFromPublicKey (Función)](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfrompublickey-function.md)  
 Obtiene un token que representa una clave pública. En desuso a partir de la [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [Estructura de nombres seguros](http://msdn.microsoft.com/library/4b041a2f-fd12-4b91-aacd-bc3b34a5124d)  
 Describe la estructura no administrada que utiliza la API de asignación de nombres seguros para administrar la firma de ensamblados con nombre seguro...  
  
 [PublicKeyBlob (estructura)](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)  
 Representa la clave pública de un par de claves pública/privada en formato binario.  
  
## <a name="see-also"></a>Vea también  
 [ICLRStrongName (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)  
 [Referencia de API no administrada](../../../../docs/framework/unmanaged-api/index.md)
