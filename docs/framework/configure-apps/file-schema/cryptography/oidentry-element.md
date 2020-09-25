---
title: <oidEntry> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/oidMap/oidEntry
- http://schemas.microsoft.com/.NetConfiguration/v2.0#oidEntry
helpviewer_keywords:
- <oidEntry> element
- oidEntry element
ms.assetid: 22fb88b0-bf27-489c-9ca0-e65950ac136c
ms.openlocfilehash: 2207c934f5864890d9b7a5e22c43a1d53e29aaa5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91187113"
---
# <a name="oidentry-element"></a>\<oidEntry> (Elemento)

Asigna un identificador de objeto (OID) ASN.1 a un nombre descriptivo.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oidMap>**](oidmap-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<oidEntry>**

## <a name="syntax"></a>Sintaxis  
  
```xml  
<oidEntry OID="object identifier number" name="friendly name" />  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  

 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|**OID**|Atributo necesario.<br /><br /> Especifica el OID ASN. 1 correspondiente al algoritmo implementado por la clase.|  
|**name**|Atributo necesario.<br /><br /> Especifica el valor para el atributo de **nombre** en la [\<nameEntry>](nameentry-element.md) etiqueta.|  
  
### <a name="child-elements"></a>Elementos secundarios  

 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`cryptographySettings`|Contiene la configuración de criptografía.|  
|`mscorlib`|Contiene el `cryptographySettings` elemento.|  
|`oidMap`|Contiene las asignaciones de identificador de objetos (OID) ASN. 1 a las clases.|  
  
## <a name="remarks"></a>Observaciones  

 Los identificadores de objeto ASN. 1 identifican los algoritmos en algunos formatos criptográficos. Asigne identificadores de objeto a nombres descriptivos para los algoritmos que desee identificar.  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se muestra cómo usar el **\<oidEntry>** elemento para asignar un identificador de objeto para el algoritmo hash RIPEMD-160 a una implementación de ese algoritmo hash.  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCrypto="MyCryptoClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="RIPEMD-160" class="MyCrypto"/>  
         </cryptoNameMapping>  
         <oidMap>  
            <oidEntry OID="1.3.36.3.2.1"   name="MyCryptoClass"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también

- [Esquema de los archivos de configuración](../index.md)
- [Esquema de configuración de criptografía](index.md)
- [servicios criptográficos](../../../../standard/security/cryptographic-services.md)
- [Configurar clases de criptografía](../../configure-cryptography-classes.md)
- [Asignar identificadores de objeto a algoritmos de criptografía](../../map-object-identifiers-to-cryptography-algorithms.md)
