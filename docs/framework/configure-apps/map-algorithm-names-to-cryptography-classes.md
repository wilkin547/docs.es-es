---
title: "Asignar nombres de algoritmo a clases de criptograf&#237;a | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "algoritmos criptográficos"
  - "criptografía, asignar nombres de algoritmo"
  - "asignar nombres de algoritmo"
  - "nombres [.NET Framework], asignación de algoritmo"
ms.assetid: 01327c69-c5e1-4ef6-b73f-0a58351f0492
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 10
---
# Asignar nombres de algoritmo a clases de criptograf&#237;a
Los desarrolladores disponen de cuatro maneras de crear un objeto criptográfico mediante [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)]:  
  
-   Crear un objeto mediante el operador **new**.  
  
-   Crear un objeto que implementa un algoritmo de criptografía concreto llamando al método **Create** en la clase abstracta de ese algoritmo.  
  
-   Crear un objeto que implementa un algoritmo de criptografía concreto llamando al método [System.Security.Cryptography.CryptoConfig.CreateFromName](frlrfSystemSecurityCryptographyCryptoConfigClassCreateFromNameTopic).  
  
-   Crear un objeto que implementa una clase de algoritmos de criptografía \(como un cifrado de bloques simétrico\) llamando al método **Create** en la clase abstracta de ese tipo de algoritmo \(como <xref:System.Security.Cryptography.SymmetricAlgorithm>\).  
  
 Por ejemplo, supongamos que un desarrollador desea calcular el hash SHA1 de un conjunto de bytes.  El espacio de nombres <xref:System.Security.Cryptography> contiene dos implementaciones del algoritmo SHA1, una implementación estrictamente administrada y otra que contiene CryptoAPI.  El desarrollador puede decidir crear una instancia de una implementación SHA1 concreta \(como la [clase SHA1Managed](frlrfSystemSecurityCryptographySHA1ManagedClassTopic)\) llamando al operador **new**.  Sin embargo, si no importa que clase carga el Common Language Runtime siempre y cuando la clase cargue el algoritmo de hash SHA1, el desarrollador puede crear un objeto llamando al método [System.Security.Cryptography.SHA1.Create](frlrfSystemSecurityCryptographySHA1ClassCreateTopic).  Este método llama a **System.Security.Cryptography.CryptoConfig.CreateFromName\("System.Security.Cryptography.SHA1"\)**, que debe devolver una implementación del algoritmo de hash SHA1.  
  
 El desarrollador puede llamar también a **System.Security.Cryptography.CryptoConfig.CreateFromName\("SHA1"\)** porque, de manera predeterminada, la configuración de criptografía contiene nombres breves para los algoritmos que se suministran con .NET Framework.  
  
 Si no importa qué algoritmo hash se usa, el desarrollador puede llamar al método [System.Security.Cryptography.HashAlgorithm.Create](frlrfSystemSecurityCryptographyHashAlgorithmClassCreateTopic), que devuelve un objeto que implementa una transformación de hash.  
  
## Asignar nombres de algoritmo en los archivos de configuración  
 De manera predeterminada, el tiempo de ejecución devuelve un objeto de la clase [System.Security.Cryptography.SHA1CryptoServiceProvider](frlrfSystemSecurityCryptographySHA1CryptoServiceProviderClassTopic) para los cuatro escenarios.  Sin embargo, un administrador de equipo puede cambiar el tipo de objeto que devuelven los métodos de los dos últimos escenarios.  Para ello, hay que asignar un nombre de algoritmo descriptivo a la clase que se desea usar en el archivo de configuración del equipo \(Machine.config\).  
  
 En el ejemplo siguiente se muestra cómo se configura el tiempo de ejecución para que **System.Security.Cryptography.SHA1.Create**, **System.Security.CryptoConfig.CreateFromName\("SHA1"\)** y **System.Security.Cryptography.HashAlgorithm.Create** devuelvan un objeto `MySHA1HashClass`.  
  
```  
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
  
 Puede especificar el nombre del atributo en [\<cryptoClass\> elemento](../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md) \(los nombres del ejemplo anterior el atributo `MySHA1Hash`\).  El valor del atributo en el elemento de **\<cryptoClass\>** es una cadena que Common Language Runtime para encontrar la clase.  Se puede utilizar cualquier cadena que cumpla los requisitos especificados en [Especificar nombres de tipo completos](../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).  
  
 Muchos nombres de algoritmo se pueden asignar a la misma clase.  [\<nameEntry\> elemento](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) asigna una clase a un nombre de algoritmo.  El atributo **name** puede ser una cadena que se usa al llamar al método **System.Security.Cryptography.CryptoConfig.CreateFromName** o el nombre de una clase de criptografía abstracta del espacio de nombres <xref:System.Security.Cryptography>.  El valor del atributo de **clase** es el nombre del atributo en el elemento de **\<cryptoClass\>** .  
  
> [!NOTE]
>  Se puede obtener un algoritmo SHA1 llamando a los métodos [System.Security.Cryptography.SHA1.Create](frlrfSystemSecurityCryptographySHA1ClassCreateTopic) o **Security.CryptoConfig.CreateFromName\("SHA1"\)**.  Cada método sólo garantiza que devuelve un objeto que implementa el algoritmo SHA1.  No es necesario asignar todos los nombres descriptivos de un algoritmo a la misma clase del archivo de configuración.  
  
 Para obtener una lista de los nombres predeterminados y las clases a las que se asignan, vea [CryptoConfig \(Clase\)](frlrfSystemSecurityCryptographyCryptoConfigClassTopic).  
  
## Vea también  
 [Servicios criptográficos](../../../docs/standard/security/cryptographic-services.md)   
 [Configurar clases de criptografía](../../../docs/framework/configure-apps/configure-cryptography-classes.md)