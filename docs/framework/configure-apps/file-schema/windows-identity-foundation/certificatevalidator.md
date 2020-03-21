---
title: <certificateValidator>
ms.date: 03/30/2017
ms.assetid: 86161897-c20f-4ad8-9d7f-050c247251bf
author: BrucePerlerMS
ms.openlocfilehash: 3f3d79d3567c1714a79423b7767ce3f454b9d52d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152793"
---
# <a name="certificatevalidator"></a><span data-ttu-id="73111-101">\<certificateValidator></span><span class="sxs-lookup"><span data-stu-id="73111-101">\<certificateValidator></span></span>
<span data-ttu-id="73111-102">Especifica un tipo personalizado para la validación de certificados.</span><span class="sxs-lookup"><span data-stu-id="73111-102">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="73111-103">Este tipo solo se `certificateValidationMode` utiliza si el atributo del [ \<](certificatevalidation.md) elemento certificateValidation>se establece en "Custom".</span><span class="sxs-lookup"><span data-stu-id="73111-103">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element is set to "Custom".</span></span>  
  
<span data-ttu-id="73111-104">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="73111-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="73111-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="73111-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="73111-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="73111-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="73111-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<certificateValidation>**](certificatevalidation.md)</span><span class="sxs-lookup"><span data-stu-id="73111-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<certificateValidation>**](certificatevalidation.md)</span></span>\
<span data-ttu-id="73111-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateValidator>**</span><span class="sxs-lookup"><span data-stu-id="73111-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateValidator>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73111-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="73111-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="73111-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="73111-110">Attributes and Elements</span></span>  
 <span data-ttu-id="73111-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="73111-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="73111-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="73111-112">Attributes</span></span>  
  
|<span data-ttu-id="73111-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="73111-113">Attribute</span></span>|<span data-ttu-id="73111-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="73111-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="73111-115">type</span><span class="sxs-lookup"><span data-stu-id="73111-115">type</span></span>|<span data-ttu-id="73111-116">Especifica un tipo personalizado que <xref:System.IdentityModel.Selectors.X509CertificateValidator> deriva de la clase.</span><span class="sxs-lookup"><span data-stu-id="73111-116">Specifies a custom type that derives from the <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span> <span data-ttu-id="73111-117">Establezca `certificateValidationMode` el atributo del [ \<](certificatevalidation.md) elemento certificateValidation>en "Custom" para usar este tipo.</span><span class="sxs-lookup"><span data-stu-id="73111-117">Set the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element to "Custom" to use this type.</span></span> <span data-ttu-id="73111-118">Para obtener más información `type` sobre cómo especificar el atributo, vea Referencias de [tipo personalizadas](../windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="73111-118">For more information about how to specify the `type` attribute, see [Custom Type References](../windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="73111-119">Opcional.</span><span class="sxs-lookup"><span data-stu-id="73111-119">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="73111-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="73111-120">Child Elements</span></span>  
 <span data-ttu-id="73111-121">None</span><span class="sxs-lookup"><span data-stu-id="73111-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="73111-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="73111-122">Parent Elements</span></span>  
  
|<span data-ttu-id="73111-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="73111-123">Element</span></span>|<span data-ttu-id="73111-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="73111-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="73111-125">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="73111-125">\<certificateValidation></span></span>](certificatevalidation.md)|<span data-ttu-id="73111-126">Controla la configuración que usan los controladores de tokens para validar certificados.</span><span class="sxs-lookup"><span data-stu-id="73111-126">Controls the settings that token handlers use to validate certificates.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="73111-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="73111-127">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="Custom"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine">  
    <certificateValidator type="MyNamespace.CustomValidator, MyAssembly" />
</certificateValidation>
```
