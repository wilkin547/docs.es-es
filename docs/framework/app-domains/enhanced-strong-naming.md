---
title: "Nombres seguros mejorados | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "nombres seguros [.NET Framework], mejorados"
  - "ensamblados con nombre seguro"
ms.assetid: 6cf17a82-62a1-4f6d-8d5a-d7d06dec2bb5
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# Nombres seguros mejorados
Una signatura de nombre seguro es un mecanismo de identidad en .NET Framework para identificar los ensamblados.  Es una signatura digital de clave pública que se utiliza normalmente para comprobar la integridad de los datos que se pasan de un emisor \(autor\) a un destinatario \(comprobador\).  Esta signatura se utiliza como identidad única para un ensamblado y garantiza que las referencias al ensamblado no sean ambiguas.  Se firma el ensamblado como parte del proceso de compilación y se comprueba cuando se carga.  
  
 Las signaturas de nombres seguros ayudan a evitar que las partes malintencionadas manipulen un ensamblado y después firmen el ensamblado nuevamente con la clave del firmante original.  Sin embargo, las claves de nombre seguro no contienen ninguna información confiable sobre el editor, ni contienen una jerarquía de certificados.  Una signatura de nombre seguro no garantiza la confiabilidad de la persona que firmó el ensamblado ni indica si esa persona era propietario legítimo de la clave; solo indica que el propietario de la clave firmó el ensamblado.  Por consiguiente, no se recomienda el uso de una signatura de nombre seguro como un validador de seguridad para confiar en código de terceros.  Microsoft Authenticode es la manera recomendada de autenticar código.  
  
## Limitaciones de nombres seguros convencionales  
 La tecnología de nombres seguros utilizada en las versiones anteriores a [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] tiene las limitaciones siguientes:  
  
-   Las claves están constantemente bajo ataque y las técnicas mejores y el hardware hacen que sea más fácil deducir la clave privada a partir de una clave pública.  Para protegerse de ataques son necesarias claves más largas. Las versiones de .NET Framework antes del [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] proporcionan la capacidad de firmar con una clave de cualquier tamaño \(el tamaño predeterminado es de 1024 bits\), pero firmar un ensamblado con una nueva clave rompe todos los binarios que hacen referencia a la identidad anterior del ensamblador.  Por lo tanto, es extremadamente difícil actualizar el tamaño de una clave de firma si se desea mantener la compatibilidad.  
  
-   Las firmas de nombre seguro sólo son compatibles con el algoritmo SHA\-1.  SHA\-1 se ha encontrado recientemente inadecuado para aplicaciones de hash seguras.  Por consiguiente, un algoritmo más seguro \(SHA\-256 o superior\) es necesario.  Es posible que SHA\-1 pierda su posición conforme a FIPS, que presentará problemas para los que elijan utilizar únicamente software y algoritmos conforme a FIPS.  
  
## Ventajas de los nombres seguros mejorados  
 Las ventajas principales de los nombres seguros mejorados son la compatibilidad con los nombres seguros preexistentes y la capacidad de demandar que una identidad sea equivalente a otra:  
  
-   Los desarrolladores con ensamblados firmados preexistentes pueden migrar sus identidades a algoritmos SHA\-2 mientras mantienen la compatibilidad con ensamblados que hacen referencia a las antiguas identidades.  
  
-   Los programadores que crean nuevos ensamblados y no se preocupan de signaturas preexistentes de nombre seguro pueden utilizar los algoritmos SHA\-2 más seguros y firmar los ensamblados como siempre lo han hecho.  
  
## Usar nombres seguros mejorados  
 Las claves de nombre seguro constan de una clave de signatura y una clave de identidad.  Se firma el ensamblado con la clave de signatura y se identifica por la clave de identidad.  Antes de [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], estas dos claves eran idénticas.  A partir de [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], la clave de identidad es igual que en versiones anteriores de .NET Framework, pero la signatura se extiende con un algoritmo hash más seguro.  Además, la clave de signatura se firma con la clave de identidad para crear una contrafirma.  
  
 El atributo <xref:System.Reflection.AssemblySignatureKeyAttribute> permite a los metadatos del ensamblado utilizar la clave pública preexistente para la identidad del ensamblado, que facilita antiguas referencias de ensamblaje para seguir trabajando.  El atributo <xref:System.Reflection.AssemblySignatureKeyAttribute> utiliza la contrafirma para garantizar que el propietario de la nueva clave de signatura también es el propietario de la antigua clave de identidad.  
  
### Firmar con SHA\-2, sin la migración de clave  
 Ejecute los siguientes comandos desde una ventana de símbolo del sistema para firmar un ensamblado sin migrar una signatura de nombre seguro:  
  
1.  Genere la nueva clave de identidad \(si es necesario\).  
  
    ```  
    sn -k IdentityKey.snk  
    ```  
  
2.  Extraiga la clave pública de identidad y especifique que un algoritmo SHA\-2 debe ser utilizado al firmar con esta clave.  
  
    ```  
    sn -p IdentityKey.snk IdentityPubKey.snk sha256  
    ```  
  
3.  Retraso al firmar el ensamblado con el archivo de identidad de clave pública.  
  
    ```  
    csc MyAssembly.cs /keyfile:IdentityPubKey.snk /delaySign+  
    ```  
  
4.  Vuelva a firmar el ensamblado con el par completo de claves de identidad.  
  
    ```  
    sn -Ra MyAssembly.exe IdentityKey.snk  
    ```  
  
### Firmar con SHA\-2, con la migración de clave  
 Ejecute los siguientes comandos desde una ventana de símbolo del sistema para firmar un ensamblado con una signatura de nombre seguro migrada.  
  
1.  Genere una clave par de identidad y signatura \(si es necesario\).  
  
    ```  
    sn -k IdentityKey.snk  
    sn -k SignatureKey.snk  
    ```  
  
2.  Extraiga la clave pública de signatura y especifique que un algoritmo SHA\-2 debe ser utilizado al firmar con esta clave.  
  
    ```  
    sn -p SignatureKey.snk SignaturePubKey.snk sha256  
    ```  
  
3.  Extraiga la clave pública de identidad, que determina el algoritmo hash que genera una contrasignatura.  
  
    ```  
    sn -p IdentityKey.snk IdentityPubKey.snk  
    ```  
  
4.  Genere los parámetros para un atributo <xref:System.Reflection.AssemblySignatureKeyAttribute> y adjunte el atributo al ensamblado.  
  
    ```  
    sn -ac IdentityPubKey.snk IdentityKey.snk SignaturePubKey.snk  
    ```  
  
5.  Retraso al firmar el ensamblado con la clave pública de identidad.  
  
    ```  
    csc MyAssembly.cs /keyfile:IdentityPubKey.snk /delaySign+  
  
    ```  
  
6.  Firme por completo el ensamblado con el par de claves de signatura.  
  
    ```  
    sn -Ra MyAssembly.exe SignatureKey.snk  
    ```  
  
## Vea también  
 [Crear y utilizar ensamblados con nombre seguro](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)