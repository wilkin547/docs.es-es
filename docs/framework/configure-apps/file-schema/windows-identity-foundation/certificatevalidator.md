---
title: <certificateValidator>
ms.date: 03/30/2017
ms.assetid: 86161897-c20f-4ad8-9d7f-050c247251bf
author: BrucePerlerMS
ms.openlocfilehash: 30f81dd5948a7d366c1116cffd347c85a396f5ae
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252123"
---
# <a name="certificatevalidator"></a><span data-ttu-id="bc317-101">\<certificateValidator></span><span class="sxs-lookup"><span data-stu-id="bc317-101">\<certificateValidator></span></span>
<span data-ttu-id="bc317-102">Especifica un tipo personalizado para la validación del certificado.</span><span class="sxs-lookup"><span data-stu-id="bc317-102">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="bc317-103">Este tipo solo se utiliza si el `certificateValidationMode` atributo [ \<del elemento > certificateValidation](certificatevalidation.md) se establece en "Custom".</span><span class="sxs-lookup"><span data-stu-id="bc317-103">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element is set to "Custom".</span></span>  
  
<span data-ttu-id="bc317-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="bc317-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="bc317-105">&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="bc317-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="bc317-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identityConfiguration**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="bc317-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="bc317-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> certificateValidation**](certificatevalidation.md)</span><span class="sxs-lookup"><span data-stu-id="bc317-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<certificateValidation>**](certificatevalidation.md)</span></span>\
<span data-ttu-id="bc317-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> certificateValidator**</span><span class="sxs-lookup"><span data-stu-id="bc317-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateValidator>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc317-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bc317-109">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <certificateValidation>  
      <certificateValidator type=xs:string>  
      </certificateValidator>  
    </certificateValidation>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bc317-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="bc317-110">Attributes and Elements</span></span>  
 <span data-ttu-id="bc317-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="bc317-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bc317-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="bc317-112">Attributes</span></span>  
  
|<span data-ttu-id="bc317-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="bc317-113">Attribute</span></span>|<span data-ttu-id="bc317-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="bc317-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bc317-115">type</span><span class="sxs-lookup"><span data-stu-id="bc317-115">type</span></span>|<span data-ttu-id="bc317-116">Especifica un tipo personalizado que deriva de la <xref:System.IdentityModel.Selectors.X509CertificateValidator> clase.</span><span class="sxs-lookup"><span data-stu-id="bc317-116">Specifies a custom type that derives from the <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span> <span data-ttu-id="bc317-117">Establezca el `certificateValidationMode` atributo [ \<](certificatevalidation.md) del elemento > de certificateValidation en "Custom" para usar este tipo.</span><span class="sxs-lookup"><span data-stu-id="bc317-117">Set the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element to "Custom" to use this type.</span></span> <span data-ttu-id="bc317-118">Para obtener más información sobre cómo especificar el `type` atributo, vea [referencias de tipo personalizado](../windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="bc317-118">For more information about how to specify the `type` attribute, see [Custom Type References](../windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="bc317-119">Opcional.</span><span class="sxs-lookup"><span data-stu-id="bc317-119">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bc317-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="bc317-120">Child Elements</span></span>  
 <span data-ttu-id="bc317-121">None</span><span class="sxs-lookup"><span data-stu-id="bc317-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bc317-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="bc317-122">Parent Elements</span></span>  
  
|<span data-ttu-id="bc317-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="bc317-123">Element</span></span>|<span data-ttu-id="bc317-124">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="bc317-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bc317-125">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="bc317-125">\<certificateValidation></span></span>](certificatevalidation.md)|<span data-ttu-id="bc317-126">Controla la configuración que usan los controladores de token para validar certificados.</span><span class="sxs-lookup"><span data-stu-id="bc317-126">Controls the settings that token handlers use to validate certificates.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="bc317-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bc317-127">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="Custom"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine">  
    <certificateValidator type="MyNamespace.CustomValidator, MyAssembly" />    
</certificateValidation>        
```
