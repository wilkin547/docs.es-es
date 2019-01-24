---
title: Asignar nombres de algoritmo a clases de criptografía
ms.date: 03/30/2017
helpviewer_keywords:
- mapping algorithm names
- cryptography, mapping algorithm names
- cryptographic algorithms
- names [.NET Framework], algorithm mapping
ms.assetid: 01327c69-c5e1-4ef6-b73f-0a58351f0492
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 87b428fffac98b4490a67e4713b56ec6e8fdcfe9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54569198"
---
# <a name="mapping-algorithm-names-to-cryptography-classes"></a>Asignar nombres de algoritmo a clases de criptografía
Hay cuatro maneras que un desarrollador puede crear un objeto de criptografía mediante el [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)]:  
  
-   Crear un objeto mediante el **nuevo** operador.  
  
-   Crear un objeto que implementa un algoritmo de criptografía concreto mediante una llamada a la **Create** método en la clase abstracta para el algoritmo.  
  
-   Crear un objeto que implementa un algoritmo de criptografía concreto mediante una llamada a la <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> método.  
  
-   Crear un objeto que implementa una clase de algoritmos de cifrado (por ejemplo, un cifrado por bloques simétrico) mediante una llamada a la **crear** método en la clase abstracta de ese tipo de algoritmo (como <xref:System.Security.Cryptography.SymmetricAlgorithm>).  
  
 Por ejemplo, suponga que un programador desea calcular el hash SHA1 de un conjunto de bytes. El <xref:System.Security.Cryptography> espacio de nombres contiene dos implementaciones del algoritmo SHA1, una implementación estrictamente administrada y otra que contiene CryptoAPI. El desarrollador puede decidir crear una instancia de una implementación SHA1 concreta (como la <xref:System.Security.Cryptography.SHA1Managed>) mediante una llamada a la **nuevo** operador. Sin embargo, si no importa qué clase de common language runtime carga siempre y cuando la clase implementa el algoritmo hash SHA1, el desarrollador puede crear un objeto mediante una llamada a la <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> método. Este método llama a **System.Security.Cryptography.CryptoConfig.CreateFromName("System.Security.Cryptography.SHA1")**, que debe devolver una implementación del algoritmo hash SHA1.  
  
 El desarrollador también puede llamar a **System.Security.Cryptography.CryptoConfig.CreateFromName("SHA1")** porque, de forma predeterminada, la configuración de criptografía contiene nombres cortos para los algoritmos que se incluye en .NET Framework.  
  
 Si no importa qué algoritmo hash se usa, el programador puede llamar a la <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> método, que devuelve un objeto que implementa una transformación de hash.  
  
## <a name="mapping-algorithm-names-in-configuration-files"></a>Asignar nombres de algoritmo en los archivos de configuración  
 De forma predeterminada, el tiempo de ejecución devuelve un <xref:System.Security.Cryptography.SHA1CryptoServiceProvider> objeto para los cuatro escenarios. Sin embargo, un administrador del equipo puede cambiar el tipo de objeto que devuelven los métodos en los últimos dos escenarios. Para ello, debe asignar un nombre de algoritmo descriptivo a la clase que desea usar en el archivo de configuración del equipo (Machine.config).  
  
 El ejemplo siguiente muestra cómo configurar el tiempo de ejecución para que **System.Security.Cryptography.SHA1.Create**, **System.Security.CryptoConfig.CreateFromName("SHA1")**, y  **System.Security.Cryptography.HashAlgorithm.Create** devolver un `MySHA1HashClass` objeto.  
  
```xml  
<configuration>  
   <!-- Other configuration settings. -->  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass MySHA1Hash="MySHA1HashClass, MyAssembly  
                  Culture='en', PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="SHA1" class="MySHA1Hash"/>  
            <nameEntry name="System.Security.Cryptography.SHA1"  
                       class="MySHA1Hash"/>  
            <nameEntry name="System.Security.Cryptography.HashAlgorithm"  
                       class="MySHA1Hash"/>  
         </cryptoNameMapping>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
 Puede especificar el nombre del atributo en el [< cryptoClass\> elemento](../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md) (el ejemplo anterior nombra el atributo `MySHA1Hash`). El valor del atributo en el  **\<cryptoClass >** elemento es una cadena que common language runtime utiliza para buscar la clase. Puede utilizar cualquier cadena que cumpla los requisitos especificados en [especificar nombres de tipo completos](../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).  
  
 Pueden asignar varios nombres de algoritmo a la misma clase. El [ \<nameEntry > elemento](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) una clase se asigna a un nombre de algoritmo descriptivos. El **nombre** atributo puede ser una cadena que se usa al llamar a la **System.Security.Cryptography.CryptoConfig.CreateFromName** método o el nombre de una clase abstracta de criptografía en la <xref:System.Security.Cryptography> espacio de nombres. El valor de la **clase** atributo es el nombre del atributo en el  **\<cryptoClass >** elemento.  
  
> [!NOTE]
>  Puede obtener un algoritmo SHA1 llamando el <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> o **Security.CryptoConfig.CreateFromName("SHA1")** método. Cada método sólo garantiza que devuelve un objeto que implementa el algoritmo SHA1. No es necesario que asignar cada nombre descriptivo de un algoritmo a la misma clase en el archivo de configuración.  
  
 Para obtener una lista de nombres predeterminados y las clases que se asignan, consulte <xref:System.Security.Cryptography.CryptoConfig>.  
  
## <a name="see-also"></a>Vea también
- [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md)
- [Configurar clases de criptografía](../../../docs/framework/configure-apps/configure-cryptography-classes.md)
