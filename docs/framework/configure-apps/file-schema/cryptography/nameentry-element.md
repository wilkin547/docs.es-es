---
title: <nameEntry> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#nameEntry
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/nameEntry
helpviewer_keywords:
- <nameEntry> element
- nameEntry element
ms.assetid: 7d7535e9-4b4a-4b8c-82e2-e40dff5a7821
ms.openlocfilehash: a339638587f8b544bbc1b0073553f6232ce09694
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699776"
---
# <a name="nameentry-element"></a>\<elemento > elemento nameEntry
Asigna un nombre de clase a un nombre de algoritmo descriptivo, que permite que una clase tenga varios nombres descriptivos.  
  
[ **\<configuration>** ](../configuration-element.md)  
&nbsp;&nbsp;[ **\<mscorlib >** ](mscorlib-element-for-cryptography-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<cryptographySettings >** ](cryptographysettings-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<cryptoNameMapping >** ](cryptonamemapping-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<elemento nameentry >**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<nameEntry name="friendly name" Class="class name" />  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las secciones siguientes se describen atributos, elementos secundarios y elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|**name**|Atributo necesario.<br /><br /> Especifica el nombre descriptivo del algoritmo que implementa la clase de criptografía.|  
|**clase**|Atributo necesario.<br /><br /> Especifica el valor para el atributo **Name** en el elemento [\<cryptoClass >](cryptoclass-element.md) .|  
  
### <a name="child-elements"></a>Elemento secundario  
 Ninguno.  
  
### <a name="parent-elements"></a>Elemento principal  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`system.web`|Especifica el elemento raíz de la sección de configuración de ASP.NET.|  
  
## <a name="remarks"></a>Comentarios  
 El atributo de **nombre** puede ser el nombre de una de las clases abstractas que se encuentran en el espacio de nombres <xref:System.Security.Cryptography>. Cuando se llama al método **Create** en una clase de criptografía abstracta, el nombre de la clase abstracta se pasa al método <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A>. **CreateFromName** devuelve una instancia del tipo indicado por el atributo de **clase** . Si el atributo **Name** es un nombre corto, como RSA, puede usar ese nombre al llamar al método **CreateFromName** .  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo usar el elemento **\<elemento nameentry >** para hacer referencia a una clase de criptografía y para configurar el tiempo de ejecución. Después, puede pasar la cadena "RSA" al método <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> y usar el método <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> para devolver un objeto `MyCryptoRSAClass`.  
  
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

- [Esquema de los archivos de configuración](../index.md)
- [Esquema de la configuración de criptografía](index.md)
- [Cryptographic Services](../../../../standard/security/cryptographic-services.md)
- [Configurar clases de criptografía](../../configure-cryptography-classes.md)
