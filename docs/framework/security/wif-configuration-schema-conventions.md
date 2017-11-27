---
title: "Convenciones del esquema de configuración de WIF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f7864356-f72f-4cae-995c-18e0431f8a58
caps.latest.revision: "3"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: ad367a14373487698cd13c710998f1a5e6ccb7cd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="wif-configuration-schema-conventions"></a><span data-ttu-id="a3bcb-102">Convenciones del esquema de configuración de WIF</span><span class="sxs-lookup"><span data-stu-id="a3bcb-102">WIF Configuration Schema Conventions</span></span>
<span data-ttu-id="a3bcb-103">En este tema se describen las convenciones que se emplean a lo largo de los temas de configuración de Windows Identity Foundation (WIF), así como algunas de las funciones y atributos que se usan en las secciones [\<system.identityModel>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md) y [\<system.identityModel.services>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md).</span><span class="sxs-lookup"><span data-stu-id="a3bcb-103">This topic discusses conventions used throughout the Windows Identity Foundation (WIF) configuration topics and describes some common features and attributes used in the [\<system.identityModel>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md) and the [\<system.identityModel.services>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md) sections.</span></span>  
  
<a name="BKMK_Modes"></a>   
## <a name="modes"></a><span data-ttu-id="a3bcb-104">Modos</span><span class="sxs-lookup"><span data-stu-id="a3bcb-104">Modes</span></span>  
 <span data-ttu-id="a3bcb-105">Muchos de los elementos de configuración de WIF tienen un atributo `mode`.</span><span class="sxs-lookup"><span data-stu-id="a3bcb-105">Many of the WIF configuration elements have a `mode` attribute.</span></span> <span data-ttu-id="a3bcb-106">Este atributo suele controlar la clase que se usa para llevar a cabo una determinada parte del procesamiento y los elementos de configuración que se permiten como elementos secundarios del elemento actual.</span><span class="sxs-lookup"><span data-stu-id="a3bcb-106">This attribute typically controls which class is used to do a particular part of the processing and which configuration elements are allowed as child elements of the current element.</span></span> <span data-ttu-id="a3bcb-107">Si los elementos que se incluyen en el archivo de configuración se omiten debido a la configuración del modo, se generará un error de configuración.</span><span class="sxs-lookup"><span data-stu-id="a3bcb-107">A configuration error will be raised if elements that are included in the configuration file are ignored because of the mode settings.</span></span>  
  
<a name="BKMK_TimespanValues"></a>   
## <a name="timespan-values"></a><span data-ttu-id="a3bcb-108">Valores TimeSpan</span><span class="sxs-lookup"><span data-stu-id="a3bcb-108">Timespan Values</span></span>  
 <span data-ttu-id="a3bcb-109">Mientras <xref:System.TimeSpan> se usa como tipo de un atributo, consulte el método <xref:System.TimeSpan.Parse%28System.String%29> para ver el formato permitido.</span><span class="sxs-lookup"><span data-stu-id="a3bcb-109">Where <xref:System.TimeSpan> is used as the type of an attribute, see the <xref:System.TimeSpan.Parse%28System.String%29> method to see the allowed format.</span></span> <span data-ttu-id="a3bcb-110">Este formato se ajusta a la siguiente especificación.</span><span class="sxs-lookup"><span data-stu-id="a3bcb-110">This format conforms to the following specification.</span></span>  
  
```  
[ws][-]{ d | [d.]hh:mm[:ss[.ff]] }[ws]  
```  
  
 <span data-ttu-id="a3bcb-111">Por ejemplo, "30", "30.00:00" y "30.00:00:00" significan 30 días, mientras que "00:05", "00:05:00" y "0.00:05:00.00" significan 5 minutos.</span><span class="sxs-lookup"><span data-stu-id="a3bcb-111">For example, "30", "30.00:00", "30.00:00:00" all mean 30 days; and "00:05", "00:05:00", "0.00:05:00.00" all mean 5 minutes.</span></span>  
  
<a name="BKMK_CertificateReferences"></a>   
## <a name="certificate-references"></a><span data-ttu-id="a3bcb-112">Referencias de certificados</span><span class="sxs-lookup"><span data-stu-id="a3bcb-112">Certificate References</span></span>  
 <span data-ttu-id="a3bcb-113">Varios elementos toman referencias de los certificados mediante el elemento `<certificateReference>`.</span><span class="sxs-lookup"><span data-stu-id="a3bcb-113">Several elements take references to certificates using the `<certificateReference>` element.</span></span> <span data-ttu-id="a3bcb-114">Cuando se hace referencia a un certificado, están disponibles los siguientes atributos.</span><span class="sxs-lookup"><span data-stu-id="a3bcb-114">When referencing a certificate, the following attributes are available.</span></span>  
  
|||  
|-|-|  
|`storeLocation`|<span data-ttu-id="a3bcb-115">Valor de la enumeración <xref:System.Security.Cryptography.X509Certificates.StoreLocation>: `CurrentUser` o `CurrentMachine`.</span><span class="sxs-lookup"><span data-stu-id="a3bcb-115">A value of the <xref:System.Security.Cryptography.X509Certificates.StoreLocation> enumeration: `CurrentUser` or `CurrentMachine`.</span></span>|  
|`storeName`|<span data-ttu-id="a3bcb-116">Un valor de la enumeración <xref:System.Security.Cryptography.X509Certificates.StoreName>; los más útiles para este contexto son `My` y `TrustedPeople`.</span><span class="sxs-lookup"><span data-stu-id="a3bcb-116">A value of the <xref:System.Security.Cryptography.X509Certificates.StoreName> enumeration; the most useful for this context are `My` and `TrustedPeople`.</span></span>|  
|`x509FindType`|<span data-ttu-id="a3bcb-117">Un valor de la enumeración <xref:System.Security.Cryptography.X509Certificates.X509FindType>; los más útiles para este contexto son `FindBySubjectName` y `FindByThumbprint`.</span><span class="sxs-lookup"><span data-stu-id="a3bcb-117">A value of the <xref:System.Security.Cryptography.X509Certificates.X509FindType> enumeration; the most useful for this context are `FindBySubjectName` and `FindByThumbprint`.</span></span> <span data-ttu-id="a3bcb-118">Para eliminar la posibilidad de que se produzca un error, se recomienda usar el tipo `FindByThumbprint` en entornos de producción.</span><span class="sxs-lookup"><span data-stu-id="a3bcb-118">To eliminate the chance of error, it is recommended that the `FindByThumbprint` type be used in production environments.</span></span>|  
|`findValue`|<span data-ttu-id="a3bcb-119">El valor usado para buscar el certificado, según el atributo `x509FindType`.</span><span class="sxs-lookup"><span data-stu-id="a3bcb-119">The value used to find the certificate, based on the `x509FindType` attribute.</span></span> <span data-ttu-id="a3bcb-120">Para eliminar la posibilidad de que se produzca un error, se recomienda usar el tipo `FindByThumbprint` en entornos de producción.</span><span class="sxs-lookup"><span data-stu-id="a3bcb-120">To eliminate the chance of error, it is recommended that the `FindByThumbprint` type be used in production environments.</span></span> <span data-ttu-id="a3bcb-121">Si se especifica `FindByThumbPrint`, este atributo toma un valor que es la forma de cadena hexadecimal de la huella digital del certificado (por ejemplo, "97249e1a5fa6bee5e515b82111ef524a4c91583f").</span><span class="sxs-lookup"><span data-stu-id="a3bcb-121">When `FindByThumbPrint` is specified, this attribute takes a value that is the hexadecimal-string form of the certificate thumbprint; for example, "97249e1a5fa6bee5e515b82111ef524a4c91583f".</span></span>|  
  
<a name="BKMK_CustomTypeReferences"></a>   
## <a name="custom-type-references"></a><span data-ttu-id="a3bcb-122">Referencias de tipos personalizados</span><span class="sxs-lookup"><span data-stu-id="a3bcb-122">Custom Type References</span></span>  
 <span data-ttu-id="a3bcb-123">Varios elementos hacen referencia a tipos personalizados mediante el atributo `type`.</span><span class="sxs-lookup"><span data-stu-id="a3bcb-123">Several elements reference custom types using the `type` attribute.</span></span> <span data-ttu-id="a3bcb-124">Este atributo debe especificar el nombre del tipo personalizado.</span><span class="sxs-lookup"><span data-stu-id="a3bcb-124">This attribute should specify the name of the custom type.</span></span> <span data-ttu-id="a3bcb-125">Para hacer referencia a un tipo desde la caché global de ensamblados (GAC), se debe usar un nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="a3bcb-125">To reference a type from the Global Assembly Cache (GAC), a strong name should be used.</span></span> <span data-ttu-id="a3bcb-126">Para hacer referencia a un tipo desde un ensamblado del directorio Bin/, se puede usar una referencia simple calificada con el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="a3bcb-126">To reference a type from an assembly in the Bin/ directory, a simple assembly-qualified reference may be used.</span></span> <span data-ttu-id="a3bcb-127">También se puede hacer referencia a los tipos definidos en el directorio App_Code/ especificando el nombre del tipo sin ningún ensamblado calificado.</span><span class="sxs-lookup"><span data-stu-id="a3bcb-127">Types defined in the App_Code/ directory may also be referenced by simply specifying the type name with no qualifying assembly.</span></span>  
  
 <span data-ttu-id="a3bcb-128">Los tipos personalizados deben derivarse del tipo especificado y deben proporcionar un constructor predeterminado `public` (argumento 0).</span><span class="sxs-lookup"><span data-stu-id="a3bcb-128">Custom types must be derived from the type specified and they must provide a `public` default (0 argument) constructor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3bcb-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="a3bcb-129">See Also</span></span>  
 [<span data-ttu-id="a3bcb-130">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="a3bcb-130">\<system.identityModel></span></span>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md)  
 [<span data-ttu-id="a3bcb-131">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="a3bcb-131">\<system.identityModel.services></span></span>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md)
