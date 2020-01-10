---
title: Modelo de criptografía de .NET Framework
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- cryptography [.NET Framework], model
- encryption [.NET Framework], model
ms.assetid: 12fecad4-fbab-432a-bade-2f05976a2971
ms.openlocfilehash: f0c00e4cc866c537fe26dd1ad466d6cde95bc608
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706232"
---
# <a name="net-framework-cryptography-model"></a>Modelo de criptografía de .NET Framework

.NET Framework proporciona implementaciones de numerosos algoritmos criptográficos estándar. Estos algoritmos son fáciles de usar y tienen las propiedades predeterminadas más seguras. Además, el modelo de criptografía de .NET Framework de herencia de objetos, diseño de secuencias y configuración es muy extensible.

## <a name="object-inheritance"></a>Herencia de objetos

El sistema de seguridad de .NET Framework implementa un patrón extensible de herencia de clases derivadas. La jerarquía es la siguiente:

- Clase de tipo de algoritmo, como <xref:System.Security.Cryptography.SymmetricAlgorithm>, <xref:System.Security.Cryptography.AsymmetricAlgorithm> o <xref:System.Security.Cryptography.HashAlgorithm>. Este nivel es abstracto.

- Clase de algoritmo que hereda de una clase de tipo de algoritmo, como, por ejemplo, <xref:System.Security.Cryptography.Aes>, <xref:System.Security.Cryptography.RC2> o <xref:System.Security.Cryptography.ECDiffieHellman>. Este nivel es abstracto.

- Implementación de una clase de algoritmo que hereda de una clase de algoritmo, como, por ejemplo, <xref:System.Security.Cryptography.AesManaged>, <xref:System.Security.Cryptography.RC2CryptoServiceProvider> o <xref:System.Security.Cryptography.ECDiffieHellmanCng>. Este nivel está completamente implementado.

Si se usa este modelo de clases derivadas, es fácil agregar un nuevo algoritmo o una nueva implementación de un algoritmo existente. Por ejemplo, para crear un nuevo algoritmo de clave pública, heredaría de la clase <xref:System.Security.Cryptography.AsymmetricAlgorithm>. Para crear una nueva implementación de un algoritmo específico, crearía una clase derivada no abstracta de ese algoritmo.

## <a name="how-algorithms-are-implemented-in-the-net-framework"></a>Cómo se implementan los algoritmos en .NET Framework

Como ejemplo de las distintas implementaciones disponibles de un algoritmo, considere los algoritmos simétricos. La base de todos los algoritmos simétricos es <xref:System.Security.Cryptography.SymmetricAlgorithm>, que heredan los siguientes algoritmos:

1. <xref:System.Security.Cryptography.Aes>

2. <xref:System.Security.Cryptography.DES>

3. <xref:System.Security.Cryptography.RC2>

4. <xref:System.Security.Cryptography.Rijndael>

5. <xref:System.Security.Cryptography.TripleDES>

Dos clases heredan <xref:System.Security.Cryptography.Aes>: <xref:System.Security.Cryptography.AesCryptoServiceProvider> y <xref:System.Security.Cryptography.AesManaged>. La clase <xref:System.Security.Cryptography.AesCryptoServiceProvider> es un contenedor que envuelve la implementación de Aes de la API de criptografía de Windows (CAPI), mientras que la clase <xref:System.Security.Cryptography.AesManaged> está escrita completamente en código administrado. También hay un tercer tipo de implementación, Cryptography Next Generation (CNG), además de las implementaciones administradas y de CAPI. Un ejemplo de un algoritmo CNG es <xref:System.Security.Cryptography.ECDiffieHellmanCng>. Los algoritmos CNG se encuentran disponibles en Windows Vista y versiones posteriores.

Puede elegir qué implementación es mejor para usted.  Las implementaciones administradas están disponibles en todas las plataformas compatibles con .NET Framework.  Las implementaciones de CAPI están disponibles en sistemas operativos anteriores y ya no se desarrollan. CNG es la última implementación, donde se lleva cabo el nuevo desarrollo. Sin embargo, las implementaciones administradas no disponen del certificado de Estándares de procesamiento de información federal (FIPS) y pueden ser más lentas que las clases contenedoras.

## <a name="stream-design"></a>Diseño de secuencias

El Common Language Runtime usa un diseño orientado a secuencias para implementar algoritmos simétricos y algoritmos hash. El núcleo de este diseño es la clase <xref:System.Security.Cryptography.CryptoStream>, que se deriva de la clase <xref:System.IO.Stream>. Los objetos criptográficos basados en secuencias admiten una interfaz estándar única (`CryptoStream`) para controlar la parte de transferencia de datos del objeto. Como todos los objetos se crean en una interfaz estándar, puede encadenar varios objetos (como un objeto hash seguido de un objeto de cifrado) y puede realizar diversas operaciones en los datos sin necesidad de un almacenamiento intermedio para ellos. El modelo de transmisión por secuencias también permite crear objetos a partir de objetos más pequeños. Por ejemplo, un algoritmo combinado de cifrado y hash puede verse como un solo objeto de secuencia, aunque este objeto podría generarse a partir de un conjunto de objetos de secuencia.

## <a name="cryptographic-configuration"></a>Configuración criptográfica

La configuración criptográfica le permite resolver una implementación específica de un algoritmo a un nombre de algoritmo, lo que permite la extensibilidad de las clases de criptografía de .NET Framework. Puede agregar su propia implementación de hardware o software de un algoritmo y asignar la implementación al nombre del algoritmo que quiera. Si un algoritmo no se especifica en el archivo de configuración, se usa la configuración predeterminada. Para obtener más información sobre la configuración criptográfica, vea [configurar las clases de criptografía](../../../docs/framework/configure-apps/configure-cryptography-classes.md).

## <a name="choosing-an-algorithm"></a>Elección de un algoritmo

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

  - <xref:System.Security.Cryptography.RNGCryptoServiceProvider>

- Generar una clave a partir de una contraseña:

  - <xref:System.Security.Cryptography.Rfc2898DeriveBytes>

## <a name="see-also"></a>Vea también

- [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md)
