---
title: "Convenciones del esquema de configuraci&#243;n de WIF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f7864356-f72f-4cae-995c-18e0431f8a58
caps.latest.revision: 3
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 3
---
# Convenciones del esquema de configuraci&#243;n de WIF
En este tema se tratan las convenciones utilizadas en los temas de configuración de \(WIF\) de la base de la identidad de Windows y se describen algunas características comunes y atributos utilizados en [\<system.identityModel\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md) y las secciones de [\<system.identityModel.services\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md) .  
  
<a name="BKMK_Modes"></a>   
## Modos  
 Muchos de los elementos de configuración de WIF tienen un atributo de `mode` .  Este atributo controla normalmente que la clase se utiliza para hacer una parte determinada de procesamiento y que no tienen los elementos de configuración como elementos secundarios del elemento actual.  Un error de configuración se generará si los elementos incluidos en el archivo de configuración se omiten debido a valores de modo.  
  
<a name="BKMK_TimespanValues"></a>   
## Valores de duración  
 Donde <xref:System.TimeSpan> se utiliza como tipo de un atributo, vea el método de <xref:System.TimeSpan.Parse%28System.String%29> para ver el formato permitido.  Este formato se ajusta a la especificación siguiente.  
  
```  
[ws][-]{ d | [d.]hh:mm[:ss[.ff]] }[ws]  
```  
  
 Por ejemplo, “30 ", “30.00:00”, “30.00:00: 00 " todos entre 30 días; y “00:05”, “00:05: 00 ", “0.00:05: 00,00 " todos entre 5 minutos.  
  
<a name="BKMK_CertificateReferences"></a>   
## Referencias de certificado  
 Varias referencias de la toma de los elementos a los certificados mediante el elemento de `<certificateReference>` .  Al hacer referencia a un certificado, los atributos siguientes están disponibles.  
  
|||  
|-|-|  
|`storeLocation`|Un valor de enumeración de <xref:System.Security.Cryptography.X509Certificates.StoreLocation> : `CurrentUser` o `CurrentMachine`.|  
|`storeName`|Un valor de enumeración de <xref:System.Security.Cryptography.X509Certificates.StoreName> ; el más útiles para este contexto son `My` y `TrustedPeople`.|  
|`x509FindType`|Un valor de enumeración de <xref:System.Security.Cryptography.X509Certificates.X509FindType> ; el más útiles para este contexto son `FindBySubjectName` y `FindByThumbprint`.  Para eliminar la posibilidad de error, se recomienda que `FindByThumbprint` escribe se usa en entornos de producción.|  
|`findValue`|El valor utilizado para buscar el certificado, basándose en el atributo de `x509FindType` .  Para eliminar la posibilidad de error, se recomienda que `FindByThumbprint` escribe se usa en entornos de producción.  Cuando se especifica `FindByThumbPrint` , este atributo toma un valor que es el formato de la hexadecimal\- cadena de la huella digital del certificado; por ejemplo, “97249e1a5fa6bee5e515b82111ef524a4c91583f”.|  
  
<a name="BKMK_CustomTypeReferences"></a>   
## Referencias de tipos personalizado  
 Varios tipos personalizados de referencia de los elementos mediante el atributo de `type` .  Este atributo debe especificar el nombre del tipo personalizado.  Para hacer referencia a un tipo de la caché global de ensamblados \(GAC\), un nombre seguro se debe utilizar.  Para hacer referencia a un tipo de un ensamblado en el directorio de Bin\/, una referencia simple calificado con el nombre de ensamblado se puede usar.  Los tipos definidos en el directorio de App\_Code\/pueden hacer referencia simplemente especificando el nombre de tipo sin el ensamblado necesario.  
  
 Los tipos personalizados se deben derivar del tipo especificado y deben proporcionar un constructor predeterminado de `public` \(0 argumentos\).  
  
## Vea también  
 [\<system.identityModel\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md)   
 [\<system.identityModel.services\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md)