---
title: Asignar nombres de algoritmo a clases de criptografía
ms.date: 03/30/2017
helpviewer_keywords:
- mapping algorithm names
- cryptography, mapping algorithm names
- cryptographic algorithms
- names [.NET Framework], algorithm mapping
ms.assetid: 01327c69-c5e1-4ef6-b73f-0a58351f0492
ms.openlocfilehash: 513000169504473aa6dd46feaca214f58502ffd0
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "69912867"
---
# <a name="mapping-algorithm-names-to-cryptography-classes"></a>Asignar nombres de algoritmo a clases de criptografía
Hay cuatro maneras en las que un programador puede crear un objeto de criptografía mediante el Windows SDK:  
  
- Cree un objeto con el operador **New** .  
  
- Cree un objeto que implemente un algoritmo de criptografía determinado llamando al método **Create** en la clase abstracta para ese algoritmo.  
  
- Cree un objeto que implemente un algoritmo de criptografía determinado llamando al <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> método.  
  
- Cree un objeto que implemente una clase de algoritmos criptográficos (por ejemplo, un cifrado de bloques simétrico) mediante una llamada al método **Create** en la clase abstracta para ese tipo de algoritmo (por ejemplo, <xref:System.Security.Cryptography.SymmetricAlgorithm> ).  
  
 Por ejemplo, supongamos que un desarrollador desea calcular el hash SHA1 de un conjunto de bytes. El <xref:System.Security.Cryptography> espacio de nombres contiene dos implementaciones del algoritmo SHA1, una implementación estrictamente administrada y otra que contiene CryptoAPI. El desarrollador puede elegir crear una instancia de una implementación de SHA1 determinada (como <xref:System.Security.Cryptography.SHA1Managed> ) llamando al **nuevo** operador. Sin embargo, si no importa qué clase carga la Common Language Runtime siempre y cuando la clase implemente el algoritmo hash SHA1, el desarrollador puede crear un objeto llamando al <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> método. Este método llama a **System. Security. Cryptography. CryptoConfig. CreateFromName ("System. Security. Cryptography. SHA1")**, que debe devolver una implementación del algoritmo hash SHA1.  
  
 El desarrollador también puede llamar a **System. Security. Cryptography. CryptoConfig. CreateFromName ("SHA1")** porque, de forma predeterminada, la configuración de criptografía incluye nombres cortos para los algoritmos que se incluyen en el .NET Framework.  
  
 Si no importa qué algoritmo hash se usa, el desarrollador puede llamar al <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> método, que devuelve un objeto que implementa una transformación hash.  
  
## <a name="mapping-algorithm-names-in-configuration-files"></a>Asignar nombres de algoritmo en archivos de configuración  
 De forma predeterminada, el tiempo de ejecución devuelve un <xref:System.Security.Cryptography.SHA1CryptoServiceProvider> objeto para los cuatro escenarios. Sin embargo, un administrador del equipo puede cambiar el tipo de objeto que devuelven los métodos de los dos últimos escenarios. Para ello, debe asignar un nombre de algoritmo descriptivo a la clase que desea utilizar en el archivo de configuración del equipo (Machine. config).  
  
 En el ejemplo siguiente se muestra cómo configurar el tiempo de ejecución para que **System. Security. Cryptography. SHA1. Create**, **System. Security. CryptoConfig. CREATEFROMNAME ("SHA1")** y **System. Security. Cryptography. HashAlgorithm. Create** devuelvan un `MySHA1HashClass` objeto.  
  
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
  
 Puede especificar el nombre del atributo en el [ \> elemento<cryptoClass](./file-schema/cryptography/cryptoclass-element.md) (el ejemplo anterior nombra el atributo `MySHA1Hash` ). El valor del atributo en el **\<cryptoClass>** elemento es una cadena que el Common Language Runtime utiliza para buscar la clase. Puede usar cualquier cadena que cumpla los requisitos especificados en [especificar nombres de tipo completos](../reflection-and-codedom/specifying-fully-qualified-type-names.md).  
  
 Muchos nombres de algoritmos se pueden asignar a la misma clase. El [ \<nameEntry> elemento](./file-schema/cryptography/nameentry-element.md) asigna una clase a un nombre de algoritmo descriptivo. El atributo de **nombre** puede ser una cadena que se usa al llamar al método **System. Security. Cryptography. CryptoConfig. CreateFromName** o el nombre de una clase de criptografía abstracta en el <xref:System.Security.Cryptography> espacio de nombres. El valor del atributo **Class** es el nombre del atributo en el **\<cryptoClass>** elemento.  
  
> [!NOTE]
> Puede obtener un algoritmo SHA1 llamando a <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> o al método **Security. CryptoConfig. CreateFromName ("SHA1")** . Cada método garantiza solo que devuelve un objeto que implementa el algoritmo SHA1. No es necesario asignar cada nombre descriptivo de un algoritmo a la misma clase en el archivo de configuración.  
  
 Para obtener una lista de los nombres predeterminados y las clases a las que se asignan, vea <xref:System.Security.Cryptography.CryptoConfig> .  
  
## <a name="see-also"></a>Consulte también

- [Servicios criptográficos](../../standard/security/cryptographic-services.md)
- [Configurar clases de criptografía](configure-cryptography-classes.md)
