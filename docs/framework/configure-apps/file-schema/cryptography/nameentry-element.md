---
title: '&lt;nameEntry&gt; elemento'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#nameEntry
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/nameEntry
helpviewer_keywords:
- <nameEntry> element
- nameEntry element
ms.assetid: 7d7535e9-4b4a-4b8c-82e2-e40dff5a7821
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 1bffb72e7c68d10e2c0edd5ec3cb9bcff10cbc0a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32743058"
---
# <a name="ltnameentrygt-element"></a>&lt;nameEntry&gt; elemento
Asigna un nombre de clase a un nombre de algoritmo descriptivo, que permite que una clase tenga varios nombres descriptivos.  
  
 \<configuration>  
\<mscorlib >  
\<cryptographySettings >  
\<cryptoNameMapping >  
\<nameEntry >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<nameEntry name="friendly name" Class="class name" />  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|**name**|Atributo necesario.<br /><br /> Especifica el nombre descriptivo del algoritmo que implementa la clase criptográfica.|  
|**class**|Atributo necesario.<br /><br /> Especifica el valor de la **nombre** de atributo en el [ \<cryptoClass >](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md) elemento.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`system.web`|Especifica el elemento raíz de la sección de configuración de ASP.NET.|  
  
## <a name="remarks"></a>Comentarios  
 El **nombre** atributo puede ser el nombre de una de las clases abstractas que se encuentra en la <xref:System.Security.Cryptography> espacio de nombres. Cuando se llama a la **crear** método en una clase abstracta de criptografía, el nombre de la clase abstracta se pasa a la <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A> método. **CreateFromName** devuelve una instancia del tipo indicado por la **clase** atributo. Si el **nombre** atributo es un nombre corto, como RSA, se puede utilizar ese nombre al llamar a la **CreateFromName** método.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo utilizar el  **\<nameEntry >** elemento para hacer referencia a una clase de criptografía y configurar el tiempo de ejecución. A continuación, puede pasar la cadena "RSA" a la <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> método y el uso el <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> método para devolver un `MyCryptoRSAClass` objeto.  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCryptoRSA="MyCryptoRSAClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="RSA" class="MyCryptoRSA"/>  
            <nameEntry name="System.Security.Cryptography.AsymmetricAlgorithm"  
                       class="MyCryptoRSA"/>  
         </cryptoNameMapping>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también  
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [Esquema de la configuración de criptografía](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 [Servicios criptográficos](../../../../../docs/standard/security/cryptographic-services.md)  
 [Configurar clases de criptografía](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
