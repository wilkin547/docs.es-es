---
title: Nombres seguros (Referencia de la API no administrada)
ms.date: 03/30/2017
helpviewer_keywords:
- strong naming [.NET Framework], using the unmanaged API
- native API reference [.NET Framework], strong naming
- unmanaged API reference [.NET Framework], strong naming
ms.assetid: 428c68b6-a7b4-44be-b280-75905f46612c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2ee08e9ca243ac086a0b75892bf9258246e8fd7c
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490665"
---
# <a name="strong-naming-unmanaged-api-reference"></a>Nombres seguros (Referencia de la API no administrada)
La API de nombres seguros permite a los clientes administrar la firma de ensamblados con nombre seguro.  
  
 Al firmar un ensamblado con un nombre seguro, se agrega un cifrado mediante clave pública al archivo que contiene el manifiesto del ensamblado. La firma con nombre seguro ayuda a comprobar la unicidad del nombre, impide la suplantación de nombres y proporciona a los llamadores una identidad única cuando se resuelve una referencia. Sin embargo, no hay ningún nivel de confianza asociado a un nombre seguro.  
  
## <a name="in-this-section"></a>En esta sección  
  
> [!NOTE]
>  Todas estas funciones han quedado en desuso a partir de .NET Framework 4. Para ver las alternativas sugeridas, consulte la interfaz [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md).  
  
 [GetHashFromAssemblyFile (Función)](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromassemblyfile-function.md)  
 Obtiene un hash del archivo de ensamblado especificado mediante un algoritmo hash concreto. Ha quedado en desuso a partir de .NET Framework 4.  
  
 [GetHashFromAssemblyFileW (Función)](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromassemblyfilew-function.md)  
 Obtiene un hash del archivo de ensamblado especificado como cadena Unicode mediante un algoritmo hash concreto. Ha quedado en desuso a partir de .NET Framework 4.  
  
 [GetHashFromBlob (Función)](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromblob-function.md)  
 Obtiene un hash del ensamblado en la dirección de memoria especificada mediante un algoritmo hash concreto. Ha quedado en desuso a partir de .NET Framework 4.  
  
 [GetHashFromFile (Función)](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfile-function.md)  
 Genera un hash a partir del contenido del archivo especificado.  Ha quedado en desuso a partir de .NET Framework 4.  
  
 [GetHashFromFileW (Función)](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfilew-function.md)  
 Genera un hash a partir del contenido del archivo especificado por una cadena Unicode. Ha quedado en desuso a partir de .NET Framework 4.  
  
 [GetHashFromHandle (Función)](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromhandle-function.md)  
 Genera un hash a partir del contenido del archivo con el identificador de archivos especificado mediante un algoritmo hash concreto.  Ha quedado en desuso a partir de .NET Framework 4.  
  
 [StrongNameCompareAssemblies (Función)](../../../../docs/framework/unmanaged-api/strong-naming/strongnamecompareassemblies-function.md)  
 Determina si dos ensamblados presentan diferencias solo mediante sus firmas de nombres seguros. Ha quedado en desuso a partir de .NET Framework 4.  
  
 [StrongNameErrorInfo (Función)](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md)  
 Obtiene el último código de error generado por una de las funciones de nombres seguros.  
  
 [StrongNameFreeBuffer (Función)](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md)  
 Libera la memoria asignada mediante una llamada anterior a una función de nombre seguro como [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfrompublickey-function.md) o [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md).   Ha quedado en desuso a partir de .NET Framework 4.  
  
 [StrongNameGetBlob (Función)](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetblob-function.md)  
 Llena el búfer especificado con la representación binaria del archivo ejecutable en la dirección especificada. Ha quedado en desuso a partir de .NET Framework 4.  
  
 [StrongNameGetBlobFromImage (Función)](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetblobfromimage-function.md)  
 Obtiene una representación binaria de la imagen de ensamblado en la dirección de memoria especificada. Ha quedado en desuso a partir de .NET Framework 4.  
  
 [StrongNameGetPublicKey (Función)](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md)  
 Obtiene la clave pública de un par de claves pública y privada. Ha quedado en desuso a partir de .NET Framework 4.  
  
 [StrongNameHashSize (Función)](../../../../docs/framework/unmanaged-api/strong-naming/strongnamehashsize-function.md)  
 Obtiene el tamaño de búfer necesario para un hash mediante el algoritmo hash especificado.  Ha quedado en desuso a partir de .NET Framework 4.  
  
 [StrongNameKeyDelete (Función)](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeydelete-function.md)  
 Elimina el contenedor de claves especificado. Ha quedado en desuso a partir de .NET Framework 4.  
  
 [StrongNameKeyGen (Función)](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeygen-function.md)  
 Crea un par de claves pública y privada para su uso en nombres seguros.  Ha quedado en desuso a partir de .NET Framework 4.  
  
 [StrongNameKeyGenEx (Función)](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeygenex-function.md)  
 Genera un par de claves pública y privada con el tamaño de clave especificado para su uso en nombres seguros. Ha quedado en desuso a partir de .NET Framework 4.  
  
 [StrongNameKeyInstall (Función)](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeyinstall-function.md)  
 Importa un par de claves pública y privada a un contenedor.  Ha quedado en desuso a partir de .NET Framework 4.  
  
 [StrongNameSignatureGeneration (Función)](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md)  
 Genera una firma de nombres seguros para el ensamblado especificado.   Ha quedado en desuso a partir de .NET Framework 4.  
  
 [StrongNameSignatureGenerationEx (Función)](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegenerationex-function.md)  
 Genera una firma de nombre seguro para el ensamblado especificado en función de las marcas indicadas.    Ha quedado en desuso a partir de .NET Framework 4.  
  
 [StrongNameSignatureSize (Función)](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturesize-function.md)  
 Devuelve el tamaño de la firma de nombre seguro. Ha quedado en desuso a partir de .NET Framework 4.  
  
 [StrongNameSignatureVerification (Función)](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverification-function.md)  
 Obtiene un valor que indica si el manifiesto del ensamblado en la ruta de acceso proporcionada contiene una firma de nombre seguro, que se comprueba según las marcas indicadas. Ha quedado en desuso a partir de .NET Framework 4.  
  
 [StrongNameSignatureVerificationEx (Función)](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverificationex-function.md)  
 Obtiene un valor que indica si el manifiesto del ensamblado en la ruta de acceso proporcionada contiene una firma de nombre seguro.  Ha quedado en desuso a partir de .NET Framework 4.  
  
 [StrongNameSignatureVerificationFromImage (Función)](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverificationfromimage-function.md)  
 Comprueba si un ensamblado que ya se ha asignado a la memoria es válido para la clave pública asociada. Ha quedado en desuso a partir de .NET Framework 4.  
  
 [StrongNameTokenFromAssembly (Función)](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassembly-function.md)  
 Crea un token de nombre seguro desde el archivo de ensamblado especificado.  Ha quedado en desuso a partir de .NET Framework 4.  
  
 [StrongNameTokenFromAssemblyEx (Función)](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassemblyex-function.md)  
 Crea un token de nombre seguro desde el archivo de ensamblado especificado y devuelve la clave pública. Ha quedado en desuso a partir de .NET Framework 4.  
  
 [StrongNameTokenFromPublicKey (Función)](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfrompublickey-function.md)  
 Obtiene un token que representa una clave pública. Ha quedado en desuso a partir de .NET Framework 4.  
  
 [PublicKeyBlob (estructura)](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)  
 Representa la clave pública de un par de claves pública y privada en formato binario.  
  
## <a name="see-also"></a>Vea también

- [ICLRStrongName (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
- [Referencia de API no administrada](../../../../docs/framework/unmanaged-api/index.md)
