---
title: '&lt;certificateValidator&gt;'
ms.date: 03/30/2017
ms.assetid: 86161897-c20f-4ad8-9d7f-050c247251bf
author: BrucePerlerMS
ms.openlocfilehash: 65b8aa6fa4422579ce0d1c5e33d3418ea051612a
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "47077660"
---
# <a name="ltcertificatevalidatorgt"></a><span data-ttu-id="06a78-102">&lt;certificateValidator&gt;</span><span class="sxs-lookup"><span data-stu-id="06a78-102">&lt;certificateValidator&gt;</span></span>
<span data-ttu-id="06a78-103">Especifica un tipo personalizado para la validación del certificado.</span><span class="sxs-lookup"><span data-stu-id="06a78-103">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="06a78-104">Este tipo se usa únicamente si el `certificateValidationMode` atributo de la [ \<certificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) está establecida en "Custom".</span><span class="sxs-lookup"><span data-stu-id="06a78-104">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) element is set to "Custom".</span></span>  
  
 <span data-ttu-id="06a78-105">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="06a78-105">\<system.identityModel></span></span>  
<span data-ttu-id="06a78-106">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="06a78-106">\<identityConfiguration></span></span>  
<span data-ttu-id="06a78-107">\<certificateValidation ></span><span class="sxs-lookup"><span data-stu-id="06a78-107">\<certificateValidation></span></span>  
<span data-ttu-id="06a78-108">\<certificateValidator ></span><span class="sxs-lookup"><span data-stu-id="06a78-108">\<certificateValidator></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06a78-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="06a78-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="06a78-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="06a78-110">Attributes and Elements</span></span>  
 <span data-ttu-id="06a78-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="06a78-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="06a78-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="06a78-112">Attributes</span></span>  
  
|<span data-ttu-id="06a78-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="06a78-113">Attribute</span></span>|<span data-ttu-id="06a78-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="06a78-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="06a78-115">type</span><span class="sxs-lookup"><span data-stu-id="06a78-115">type</span></span>|<span data-ttu-id="06a78-116">Especifica un tipo personalizado que deriva la <xref:System.IdentityModel.Selectors.X509CertificateValidator> clase.</span><span class="sxs-lookup"><span data-stu-id="06a78-116">Specifies a custom type that derives from the <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span> <span data-ttu-id="06a78-117">Establecer el `certificateValidationMode` atributo de la [ \<certificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) "Personalizar" para usar este tipo de elemento.</span><span class="sxs-lookup"><span data-stu-id="06a78-117">Set the `certificateValidationMode` attribute of the [\<certificateValidation>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) element to "Custom" to use this type.</span></span> <span data-ttu-id="06a78-118">Para obtener más información sobre cómo especificar el `type` atributo, vea [referencias de tipos personalizado](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="06a78-118">For more information about how to specify the `type` attribute, see [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="06a78-119">Opcional.</span><span class="sxs-lookup"><span data-stu-id="06a78-119">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="06a78-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="06a78-120">Child Elements</span></span>  
 <span data-ttu-id="06a78-121">Ninguna</span><span class="sxs-lookup"><span data-stu-id="06a78-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="06a78-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="06a78-122">Parent Elements</span></span>  
  
|<span data-ttu-id="06a78-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="06a78-123">Element</span></span>|<span data-ttu-id="06a78-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="06a78-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="06a78-125">\<certificateValidation ></span><span class="sxs-lookup"><span data-stu-id="06a78-125">\<certificateValidation></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|<span data-ttu-id="06a78-126">Controla la configuración que los controladores de token que se usan para validar los certificados.</span><span class="sxs-lookup"><span data-stu-id="06a78-126">Controls the settings that token handlers use to validate certificates.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="06a78-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="06a78-127">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="Custom"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine">  
    <certificateValidator type="MyNamespace.CustomValidator, MyAssembly" />    
</certificateValidation>        
```
