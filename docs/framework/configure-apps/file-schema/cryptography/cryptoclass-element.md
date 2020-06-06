---
title: <cryptoClass> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/cryptoClasses/cryptoClass
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoClass
helpviewer_keywords:
- cryptoClass element
- <cryptoClass> element
ms.assetid: 03db52ef-010e-44ea-b6fd-b9c900ecad50
ms.openlocfilehash: 4872fbd6fa043902e8c69f158bee5d0c915ec83a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "74088658"
---
# <a name="cryptoclass-element"></a>\<cryptoClass> (Elemento)
Contiene una clase de criptografía que tiene una asignación a un nombre descriptivo en el [\<nameEntry>](nameentry-element.md) elemento.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoClasses>**](cryptoclasses-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptoClass>**

## <a name="syntax"></a>Sintaxis  
  
```xml  
<cryptoClass customClassName="fully qualified type name" />  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`customClassName`|Atributo necesario.<br /><br /> Contiene la información de la clase de criptografía. Use este atributo para proporcionar un nombre corto para la clase. Debe especificar una cadena que cumpla los requisitos especificados en [especificar nombres de tipo completos](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`cryptoClasses`|Contiene una lista de las clases de criptografía que tienen una asignación a un nombre descriptivo en el [\<nameEntry>](nameentry-element.md) elemento.|  
|`cryptographySettings`|Contiene la configuración de criptografía.|  
|`cryptoNameMapping`|Contiene asignaciones de clases a nombres descriptivos.|  
|`mscorlib`|Contiene el [\<cryptographySettings>](cryptographysettings-element.md) elemento.|  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo usar el **\<cryptoClass>** elemento para hacer referencia a una clase de criptografía y configurar el tiempo de ejecución. Después, puede pasar la cadena "RSA" al <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> método y usar el <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> método para devolver un `MyCryptoRSAClass` objeto.  
  
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
- [Servicios criptográficos](../../../../standard/security/cryptographic-services.md)
- [Configurar clases de criptografía](../../configure-cryptography-classes.md)
