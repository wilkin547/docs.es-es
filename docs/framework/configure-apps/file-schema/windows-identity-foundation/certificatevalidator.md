---
title: '&lt;certificateValidator&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 86161897-c20f-4ad8-9d7f-050c247251bf
caps.latest.revision: "6"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 74dd0827ee073d57c82729ec1e6a9a672aa1f404
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="ltcertificatevalidatorgt"></a><span data-ttu-id="45634-102">&lt;certificateValidator&gt;</span><span class="sxs-lookup"><span data-stu-id="45634-102">&lt;certificateValidator&gt;</span></span>
<span data-ttu-id="45634-103">Especifica un tipo personalizado para la validación del certificado.</span><span class="sxs-lookup"><span data-stu-id="45634-103">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="45634-104">Este tipo se usa únicamente si la `certificateValidationMode` atributo de la [ \<certificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) elemento está establecido en "Custom".</span><span class="sxs-lookup"><span data-stu-id="45634-104">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) element is set to "Custom".</span></span>  
  
 <span data-ttu-id="45634-105">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="45634-105">\<system.identityModel></span></span>  
<span data-ttu-id="45634-106">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="45634-106">\<identityConfiguration></span></span>  
<span data-ttu-id="45634-107">\<certificateValidation ></span><span class="sxs-lookup"><span data-stu-id="45634-107">\<certificateValidation></span></span>  
<span data-ttu-id="45634-108">\<certificateValidator ></span><span class="sxs-lookup"><span data-stu-id="45634-108">\<certificateValidator></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45634-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="45634-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="45634-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="45634-110">Attributes and Elements</span></span>  
 <span data-ttu-id="45634-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="45634-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="45634-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="45634-112">Attributes</span></span>  
  
|<span data-ttu-id="45634-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="45634-113">Attribute</span></span>|<span data-ttu-id="45634-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="45634-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="45634-115">type</span><span class="sxs-lookup"><span data-stu-id="45634-115">type</span></span>|<span data-ttu-id="45634-116">Especifica un tipo personalizado que deriva de la <xref:System.IdentityModel.Selectors.X509CertificateValidator> clase.</span><span class="sxs-lookup"><span data-stu-id="45634-116">Specifies a custom type that derives from the <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span> <span data-ttu-id="45634-117">Establecer el `certificateValidationMode` atributo de la [ \<certificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) elemento a "Custom" para usar este tipo.</span><span class="sxs-lookup"><span data-stu-id="45634-117">Set the `certificateValidationMode` attribute of the [\<certificateValidation>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) element to "Custom" to use this type.</span></span> <span data-ttu-id="45634-118">Para obtener más información sobre cómo especificar el `type` de atributo, vea [las referencias de tipos personalizado](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="45634-118">For more information about how to specify the `type` attribute, see [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="45634-119">Opcional.</span><span class="sxs-lookup"><span data-stu-id="45634-119">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="45634-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="45634-120">Child Elements</span></span>  
 <span data-ttu-id="45634-121">Ninguna</span><span class="sxs-lookup"><span data-stu-id="45634-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="45634-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="45634-122">Parent Elements</span></span>  
  
|<span data-ttu-id="45634-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="45634-123">Element</span></span>|<span data-ttu-id="45634-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="45634-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="45634-125">\<certificateValidation ></span><span class="sxs-lookup"><span data-stu-id="45634-125">\<certificateValidation></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|<span data-ttu-id="45634-126">Controla la configuración que usan los controladores de tokens para validar certificados.</span><span class="sxs-lookup"><span data-stu-id="45634-126">Controls the settings that token handlers use to validate certificates.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="45634-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="45634-127">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="Custom"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine">  
    <certificateValidator type="MyNamespace.CustomValidator, MyAssembly" />    
</certificateValidation>        
```
