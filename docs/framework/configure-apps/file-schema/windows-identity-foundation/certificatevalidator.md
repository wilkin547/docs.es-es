---
title: <certificateValidator>
ms.date: 03/30/2017
ms.assetid: 86161897-c20f-4ad8-9d7f-050c247251bf
author: BrucePerlerMS
ms.openlocfilehash: c25f183679f41f51ffee4f482bfe7a64763647d9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941900"
---
# <a name="certificatevalidator"></a><span data-ttu-id="401f8-101">\<certificateValidator></span><span class="sxs-lookup"><span data-stu-id="401f8-101">\<certificateValidator></span></span>
<span data-ttu-id="401f8-102">Especifica un tipo personalizado para la validación del certificado.</span><span class="sxs-lookup"><span data-stu-id="401f8-102">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="401f8-103">Este tipo solo se utiliza si el `certificateValidationMode` atributo [ \<del elemento > certificateValidation](certificatevalidation.md) se establece en "Custom".</span><span class="sxs-lookup"><span data-stu-id="401f8-103">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element is set to "Custom".</span></span>  
  
 <span data-ttu-id="401f8-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="401f8-104">\<system.identityModel></span></span>  
<span data-ttu-id="401f8-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="401f8-105">\<identityConfiguration></span></span>  
<span data-ttu-id="401f8-106">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="401f8-106">\<certificateValidation></span></span>  
<span data-ttu-id="401f8-107">\<certificateValidator></span><span class="sxs-lookup"><span data-stu-id="401f8-107">\<certificateValidator></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="401f8-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="401f8-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="401f8-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="401f8-109">Attributes and Elements</span></span>  
 <span data-ttu-id="401f8-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="401f8-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="401f8-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="401f8-111">Attributes</span></span>  
  
|<span data-ttu-id="401f8-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="401f8-112">Attribute</span></span>|<span data-ttu-id="401f8-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="401f8-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="401f8-114">type</span><span class="sxs-lookup"><span data-stu-id="401f8-114">type</span></span>|<span data-ttu-id="401f8-115">Especifica un tipo personalizado que deriva de la <xref:System.IdentityModel.Selectors.X509CertificateValidator> clase.</span><span class="sxs-lookup"><span data-stu-id="401f8-115">Specifies a custom type that derives from the <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span> <span data-ttu-id="401f8-116">Establezca el `certificateValidationMode` atributo [ \<](certificatevalidation.md) del elemento > de certificateValidation en "Custom" para usar este tipo.</span><span class="sxs-lookup"><span data-stu-id="401f8-116">Set the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element to "Custom" to use this type.</span></span> <span data-ttu-id="401f8-117">Para obtener más información sobre cómo especificar el `type` atributo, vea [referencias de tipo personalizado](../windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="401f8-117">For more information about how to specify the `type` attribute, see [Custom Type References](../windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="401f8-118">Opcional.</span><span class="sxs-lookup"><span data-stu-id="401f8-118">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="401f8-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="401f8-119">Child Elements</span></span>  
 <span data-ttu-id="401f8-120">None</span><span class="sxs-lookup"><span data-stu-id="401f8-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="401f8-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="401f8-121">Parent Elements</span></span>  
  
|<span data-ttu-id="401f8-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="401f8-122">Element</span></span>|<span data-ttu-id="401f8-123">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="401f8-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="401f8-124">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="401f8-124">\<certificateValidation></span></span>](certificatevalidation.md)|<span data-ttu-id="401f8-125">Controla la configuración que usan los controladores de token para validar certificados.</span><span class="sxs-lookup"><span data-stu-id="401f8-125">Controls the settings that token handlers use to validate certificates.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="401f8-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="401f8-126">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="Custom"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine">  
    <certificateValidator type="MyNamespace.CustomValidator, MyAssembly" />    
</certificateValidation>        
```
