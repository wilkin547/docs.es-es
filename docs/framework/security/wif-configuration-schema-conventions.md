---
title: Convenciones del esquema de configuración de WIF
ms.date: 03/30/2017
ms.assetid: f7864356-f72f-4cae-995c-18e0431f8a58
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 3109b75ccf9cefcad4e112cca02e932ea5489d24
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33410408"
---
# <a name="wif-configuration-schema-conventions"></a>Convenciones del esquema de configuración de WIF
En este tema se describen las convenciones que se emplean a lo largo de los temas de configuración de Windows Identity Foundation (WIF), así como algunas de las funciones y atributos que se usan en las secciones [\<system.identityModel>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md) y [\<system.identityModel.services>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md).  
  
<a name="BKMK_Modes"></a>   
## <a name="modes"></a>Modos  
 Muchos de los elementos de configuración de WIF tienen un atributo `mode`. Este atributo suele controlar la clase que se usa para llevar a cabo una determinada parte del procesamiento y los elementos de configuración que se permiten como elementos secundarios del elemento actual. Si los elementos que se incluyen en el archivo de configuración se omiten debido a la configuración del modo, se generará un error de configuración.  
  
<a name="BKMK_TimespanValues"></a>   
## <a name="timespan-values"></a>Valores TimeSpan  
 Mientras <xref:System.TimeSpan> se usa como tipo de un atributo, consulte el método <xref:System.TimeSpan.Parse%28System.String%29> para ver el formato permitido. Este formato se ajusta a la siguiente especificación.  
  
```  
[ws][-]{ d | [d.]hh:mm[:ss[.ff]] }[ws]  
```  
  
 Por ejemplo, "30", "30.00:00" y "30.00:00:00" significan 30 días, mientras que "00:05", "00:05:00" y "0.00:05:00.00" significan 5 minutos.  
  
<a name="BKMK_CertificateReferences"></a>   
## <a name="certificate-references"></a>Referencias de certificados  
 Varios elementos toman referencias de los certificados mediante el elemento `<certificateReference>`. Cuando se hace referencia a un certificado, están disponibles los siguientes atributos.  
  
|||  
|-|-|  
|`storeLocation`|Valor de la enumeración <xref:System.Security.Cryptography.X509Certificates.StoreLocation>: `CurrentUser` o `CurrentMachine`.|  
|`storeName`|Un valor de la enumeración <xref:System.Security.Cryptography.X509Certificates.StoreName>; los más útiles para este contexto son `My` y `TrustedPeople`.|  
|`x509FindType`|Un valor de la enumeración <xref:System.Security.Cryptography.X509Certificates.X509FindType>; los más útiles para este contexto son `FindBySubjectName` y `FindByThumbprint`. Para eliminar la posibilidad de que se produzca un error, se recomienda usar el tipo `FindByThumbprint` en entornos de producción.|  
|`findValue`|El valor usado para buscar el certificado, según el atributo `x509FindType`. Para eliminar la posibilidad de que se produzca un error, se recomienda usar el tipo `FindByThumbprint` en entornos de producción. Si se especifica `FindByThumbPrint`, este atributo toma un valor que es la forma de cadena hexadecimal de la huella digital del certificado (por ejemplo, "97249e1a5fa6bee5e515b82111ef524a4c91583f").|  
  
<a name="BKMK_CustomTypeReferences"></a>   
## <a name="custom-type-references"></a>Referencias de tipos personalizados  
 Varios elementos hacen referencia a tipos personalizados mediante el atributo `type`. Este atributo debe especificar el nombre del tipo personalizado. Para hacer referencia a un tipo desde la caché global de ensamblados (GAC), se debe usar un nombre seguro. Para hacer referencia a un tipo desde un ensamblado del directorio Bin/, se puede usar una referencia simple calificada con el ensamblado. También se puede hacer referencia a los tipos definidos en el directorio App_Code/ especificando el nombre del tipo sin ningún ensamblado calificado.  
  
 Los tipos personalizados deben derivarse del tipo especificado y deben proporcionar un constructor predeterminado `public` (argumento 0).  
  
## <a name="see-also"></a>Vea también  
 [\<system.identityModel >](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md)  
 [\<system.identityModel.services>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md)
