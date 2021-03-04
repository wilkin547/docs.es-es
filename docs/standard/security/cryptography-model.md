---
title: Modelo de criptografía de .NET
description: Revise las implementaciones de los algoritmos criptográficos habituales en .NET. Obtenga información sobre el modelo de criptografía extensible de herencia de objetos, diseño de secuencias & configuración.
ms.date: 02/26/2021
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cryptography [.NET], model
- encryption [.NET], model
ms.assetid: 12fecad4-fbab-432a-bade-2f05976a2971
ms.openlocfilehash: 2208e36ac4521f43cfd2960d92588c8349a119ca
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102106935"
---
# <a name="net-cryptography-model"></a>Modelo de criptografía de .NET

.NET proporciona implementaciones de muchos algoritmos criptográficos estándar y el modelo de criptografía de .NET es extensible.

## <a name="object-inheritance"></a>Herencia de objetos

El sistema de criptografía de .NET implementa un patrón extensible de herencia de clases derivadas. La jerarquía es la siguiente:

- Clase de tipo de algoritmo, como <xref:System.Security.Cryptography.SymmetricAlgorithm> ,  <xref:System.Security.Cryptography.AsymmetricAlgorithm> o <xref:System.Security.Cryptography.HashAlgorithm> . Este nivel es abstracto.

- Clase de algoritmo que hereda de una clase de tipo de algoritmo, como, por ejemplo, <xref:System.Security.Cryptography.Aes>, <xref:System.Security.Cryptography.RSA> o <xref:System.Security.Cryptography.ECDiffieHellman>. Este nivel es abstracto.

- Implementación de una clase de algoritmo que hereda de una clase de algoritmo, como, por ejemplo, <xref:System.Security.Cryptography.AesManaged>, <xref:System.Security.Cryptography.RC2CryptoServiceProvider> o <xref:System.Security.Cryptography.ECDiffieHellmanCng>. Este nivel está completamente implementado.

Este patrón de clases derivadas le permite agregar un nuevo algoritmo o una nueva implementación de un algoritmo existente. Por ejemplo, para crear un nuevo algoritmo de clave pública, heredaría de la clase <xref:System.Security.Cryptography.AsymmetricAlgorithm>. Para crear una nueva implementación de un algoritmo específico, crearía una clase derivada no abstracta de ese algoritmo.

## <a name="how-algorithms-are-implemented-in-net"></a>Cómo se implementan los algoritmos en .NET

Como ejemplo de las distintas implementaciones disponibles de un algoritmo, considere los algoritmos simétricos. La base de todos los algoritmos simétricos es <xref:System.Security.Cryptography.SymmetricAlgorithm> , que es heredada por <xref:System.Security.Cryptography.Aes> , <xref:System.Security.Cryptography.TripleDES> y otras que ya no se recomiendan.

<xref:System.Security.Cryptography.Aes> es heredado por <xref:System.Security.Cryptography.AesCryptoServiceProvider> , <xref:System.Security.Cryptography.AesCng> y <xref:System.Security.Cryptography.AesManaged> .

En .NET Framework en Windows:

* `*CryptoServiceProvider` las clases de algoritmo, como <xref:System.Security.Cryptography.AesCryptoServiceProvider> , son contenedores en torno a la implementación de la API de criptografía de Windows (CAPI) de un algoritmo.
* `*Cng` las clases de algoritmo, como <xref:System.Security.Cryptography.ECDiffieHellmanCng> , son contenedores en torno a la implementación de Windows Cryptography Next Generation (CNG).
* `*Managed` las clases, como <xref:System.Security.Cryptography.AesManaged> , se escriben completamente en código administrado. `*Managed` las implementaciones no están certificadas por los estándares federales de procesamiento de información (FIPS) y pueden ser más lentas que las `*CryptoServiceProvider` `*Cng` clases contenedoras y.

En .NET Core y .NET 5 y versiones posteriores, todas las clases de implementación ( `*CryptoServiceProvider` , `*Managed` y `*Cng` ) son contenedores para los algoritmos del sistema operativo (SO). Si los algoritmos de sistema operativo están certificados por FIPS, .NET usa algoritmos con certificación FIPS. Para obtener más información, consulte [Criptografía multiplataforma](cross-platform-cryptography.md).

En la mayoría de los casos, no es necesario hacer referencia directamente a una clase de implementación de algoritmos, como `AesCryptoServiceProvider` . Los métodos y las propiedades que normalmente necesita están en la clase de algoritmo base, como `Aes` . Cree una instancia de una clase de implementación predeterminada utilizando un Factory Method en la clase de algoritmo base y haga referencia a la clase de algoritmo base. Por ejemplo, vea la línea de código resaltada en el ejemplo siguiente:

:::code language="csharp" source="snippets/encrypting-data/csharp/aes-encrypt.cs" highlight="20":::
:::code language="vb" source="snippets/encrypting-data/vb/aes-encrypt.vb" highlight="17":::

## <a name="cryptographic-configuration"></a>Configuración criptográfica

La configuración criptográfica le permite resolver una implementación específica de un algoritmo en un nombre de algoritmo, lo que permite la extensibilidad de las clases de criptografía de .NET. Puede agregar su propia implementación de hardware o software de un algoritmo y asignar la implementación al nombre del algoritmo que quiera. Si un algoritmo no se especifica en el archivo de configuración, se usa la configuración predeterminada.

## <a name="choose-an-algorithm"></a>Selección de un algoritmo

Puede seleccionar un algoritmo por diferentes motivos: por ejemplo, para proteger la integridad de los datos, para proteger la privacidad de los datos o para generar una clave. Los algoritmos simétricos y hash están diseñados para proteger los datos por motivos de integridad (impedir los cambios) o por motivos de privacidad (impedir la visualización). Los algoritmos hash se usan principalmente para proteger la integridad de los datos.

Esta es una lista de los algoritmos recomendados en función de la aplicación:

- Privacidad de los datos:
  - <xref:System.Security.Cryptography.Aes>
- Integridad de los datos:
  - <xref:System.Security.Cryptography.HMACSHA256>
  - <xref:System.Security.Cryptography.HMACSHA512>
- Firma digital:
  - <xref:System.Security.Cryptography.ECDsa>
  - <xref:System.Security.Cryptography.RSA>
- Intercambio de claves:
  - <xref:System.Security.Cryptography.ECDiffieHellman>
  - <xref:System.Security.Cryptography.RSA>
- Generación de números aleatorios:
  - <xref:System.Security.Cryptography.RandomNumberGenerator.Create%2A?displayProperty=nameWithType>
- Generar una clave a partir de una contraseña:
  - <xref:System.Security.Cryptography.Rfc2898DeriveBytes>

## <a name="see-also"></a>Consulte también

- [servicios criptográficos](cryptographic-services.md)
- [Criptografía multiplataforma](cross-platform-cryptography.md)
- [ASP.NET Core protección de datos](/aspnet/core/security/data-protection/introduction)
