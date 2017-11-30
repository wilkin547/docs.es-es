---
title: Nombres seguros mejorados
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- strong-named assemblies
- strong naming [.NET Framework], enhanced
ms.assetid: 6cf17a82-62a1-4f6d-8d5a-d7d06dec2bb5
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 429a54340cef6d608692abd71311c012afe9a3d0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="enhanced-strong-naming"></a>Nombres seguros mejorados
Una firma de nombre seguro es un mecanismo de identidad de .NET Framework para identificar ensamblados. Es una firma digital de clave pública que se suele usar para comprobar la integridad de los datos que se pasan de un remitente (firmante) a un destinatario (comprobador). Esta firma se usa como identidad única para un ensamblado y garantiza que las referencias al ensamblado no son ambiguas. El ensamblado se firma como parte del proceso de compilación y, después, se comprueba cuando se carga.  
  
 Las firmas de nombre seguro ayudan a impedir que personas malintencionadas manipulen un ensamblado y vuelvan a firmarlo con la clave del firmante original. Pero las claves de nombre seguro no contienen información confiable sobre el publicador ni una jerarquía de certificados. Una firma de nombre seguro no garantiza la confiabilidad de la persona que ha firmado el ensamblado ni indica si dicha persona era el propietario legítimo de la clave; solo indica que el propietario de la clave ha firmado el ensamblado. Por lo tanto, no se recomienda usar una firma de nombre seguro como validador de seguridad para código de terceros de confianza. La manera recomendada de autenticar el código es Microsoft Authenticode.  
  
## <a name="limitations-of-conventional-strong-names"></a>Limitaciones de los nombres seguros convencionales  
 La tecnología de nomenclatura segura usada en las versiones anteriores a [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] tiene las limitaciones siguientes:  
  
-   Las claves se encuentran constantemente bajo ataque, y las técnicas y el hardware mejorados hacen que sea más fácil deducir una clave privada a partir de una clave pública. Para protegerse contra los ataques, son necesarias claves más largas. Las versiones de .NET Framework anteriores a [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] ofrecen la posibilidad de firmar con una clave de cualquier tamaño (el tamaño predeterminado es de 1024 bits), pero si se firma un ensamblado con una clave nueva se interrumpen todos los binarios que hacen referencia a la identidad anterior del ensamblado. Por lo tanto, es muy difícil actualizar el tamaño de una clave de firma si quiere mantener la compatibilidad.  
  
-   La firma con nombre seguro solo admite el algoritmo SHA-1. Recientemente se ha descubierto que SHA-1 no es adecuado para las aplicaciones de hash seguro. Por lo tanto, es necesario un algoritmo más seguro (SHA-256 o superior). Es posible que SHA-1 pierda su compatibilidad con FIPS, lo que causaría problemas a los clientes que deciden usar solo algoritmos y software compatibles con FIPS.  
  
## <a name="advantages-of-enhanced-strong-names"></a>Ventajas de los nombres seguros mejorados  
 Las principales ventajas de los nombres seguros mejorados son la compatibilidad con los nombres seguros existentes y la capacidad de afirmar que una identidad es equivalente a otra:  
  
-   Los desarrolladores que ya tengan ensamblados firmados pueden migrar sus identidades a los algoritmos SHA-2 y mantener la compatibilidad con los ensamblados que hacen referencia a identidades anteriores.  
  
-   Los desarrolladores que creen ensamblados y no se vean afectados por las firmas de nombre seguro existentes pueden usar los algoritmos SHA-2, que son más seguros, y firmar los ensamblados tal como han hecho siempre.  
  
## <a name="using-enhanced-strong-names"></a>Usar nombres seguros mejorados  
 Las claves de nombre seguro se componen de una clave de firma y una clave de identidad. El ensamblado se firma con la clave de firma y se identifica mediante la clave de identidad. Antes de [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], estas dos claves eran idénticas. A partir de [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], la clave de identidad sigue siendo la misma que en versiones anteriores de .NET Framework, pero la clave de firma se ha mejorado con un algoritmo hash más seguro. Además, la clave de firma se firma con la clave de identidad para crear una contrafirma.  
  
 El atributo <xref:System.Reflection.AssemblySignatureKeyAttribute> permite que los metadatos del ensamblado usen la clave pública existente para la identidad del ensamblado, lo que permite que las referencias anteriores del ensamblado sigan funcionando.  El atributo <xref:System.Reflection.AssemblySignatureKeyAttribute> usa la contrafirma para asegurarse de que el propietario de la clave de firma nueva también es el propietario de la clave de identidad anterior.  
  
### <a name="signing-with-sha-2-without-key-migration"></a>Firmar con SHA-2 (sin migración de clave)  
 Ejecute los comandos siguientes desde una ventana del símbolo del sistema para firmar un ensamblado sin migrar una firma de nombre seguro:  
  
1.  Genere la nueva clave de identidad (si es necesario).  
  
    ```  
    sn -k IdentityKey.snk  
    ```  
  
2.  Extraiga la clave pública de identidad y especifique que se debe usar un algoritmo SHA-2 al firmar con esta clave.  
  
    ```  
    sn -p IdentityKey.snk IdentityPubKey.snk sha256  
    ```  
  
3.  Retrase la firma del ensamblado con el archivo de clave pública de identidad.  
  
    ```  
    csc MyAssembly.cs /keyfile:IdentityPubKey.snk /delaySign+  
    ```  
  
4.  Vuelva a firmar el ensamblado con el par de claves de identidad completa.  
  
    ```  
    sn -Ra MyAssembly.exe IdentityKey.snk  
    ```  
  
### <a name="signing-with-sha-2-with-key-migration"></a>Firmar con SHA-2 (con migración de clave)  
 Ejecute los comandos siguientes desde una ventana del símbolo del sistema para firmar un ensamblado con una firma de nombre seguro migrada.  
  
1.  Genere un par de claves de identidad y firma (si es necesario).  
  
    ```  
    sn -k IdentityKey.snk  
    sn -k SignatureKey.snk  
    ```  
  
2.  Extraiga la clave pública de firma y especifique que se debe usar un algoritmo SHA-2 al firmar con esta clave.  
  
    ```  
    sn -p SignatureKey.snk SignaturePubKey.snk sha256  
    ```  
  
3.  Extraiga la clave pública de identidad, que determina el algoritmo hash que genera una contrafirma.  
  
    ```  
    sn -p IdentityKey.snk IdentityPubKey.snk  
    ```  
  
4.  Genere los parámetros para un atributo <xref:System.Reflection.AssemblySignatureKeyAttribute> y adjunte el atributo al ensamblado.  
  
    ```  
    sn -ac IdentityPubKey.snk IdentityKey.snk SignaturePubKey.snk  
    ```  
  
5.  Retrase la firma del ensamblado con la clave pública de identidad.  
  
    ```  
    csc MyAssembly.cs /keyfile:IdentityPubKey.snk /delaySign+  
    ```  
  
6.  Firme por completo el ensamblado con el par de claves de firma.  
  
    ```  
    sn -Ra MyAssembly.exe SignatureKey.snk  
    ```  
  
## <a name="see-also"></a>Vea también  
 [Crear y utilizar ensamblados con nombre seguro](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)
