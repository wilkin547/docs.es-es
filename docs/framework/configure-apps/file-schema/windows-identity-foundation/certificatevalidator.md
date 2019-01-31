---
title: <certificateValidator>
ms.date: 03/30/2017
ms.assetid: 86161897-c20f-4ad8-9d7f-050c247251bf
author: BrucePerlerMS
ms.openlocfilehash: df52212305e0865b8c03fdd49068cb7c7da4fa38
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55277461"
---
# <a name="certificatevalidator"></a><span data-ttu-id="37f36-101">\<certificateValidator></span><span class="sxs-lookup"><span data-stu-id="37f36-101">\<certificateValidator></span></span>
<span data-ttu-id="37f36-102">Especifica un tipo personalizado para la validación del certificado.</span><span class="sxs-lookup"><span data-stu-id="37f36-102">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="37f36-103">Este tipo se usa únicamente si el `certificateValidationMode` atributo de la [ \<certificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) está establecida en "Custom".</span><span class="sxs-lookup"><span data-stu-id="37f36-103">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) element is set to "Custom".</span></span>  
  
 <span data-ttu-id="37f36-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="37f36-104">\<system.identityModel></span></span>  
<span data-ttu-id="37f36-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="37f36-105">\<identityConfiguration></span></span>  
<span data-ttu-id="37f36-106">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="37f36-106">\<certificateValidation></span></span>  
<span data-ttu-id="37f36-107">\<certificateValidator></span><span class="sxs-lookup"><span data-stu-id="37f36-107">\<certificateValidator></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37f36-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="37f36-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="37f36-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="37f36-109">Attributes and Elements</span></span>  
 <span data-ttu-id="37f36-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="37f36-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="37f36-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="37f36-111">Attributes</span></span>  
  
|<span data-ttu-id="37f36-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="37f36-112">Attribute</span></span>|<span data-ttu-id="37f36-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="37f36-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="37f36-114">type</span><span class="sxs-lookup"><span data-stu-id="37f36-114">type</span></span>|<span data-ttu-id="37f36-115">Especifica un tipo personalizado que deriva la <xref:System.IdentityModel.Selectors.X509CertificateValidator> clase.</span><span class="sxs-lookup"><span data-stu-id="37f36-115">Specifies a custom type that derives from the <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span> <span data-ttu-id="37f36-116">Establecer el `certificateValidationMode` atributo de la [ \<certificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) "Personalizar" para usar este tipo de elemento.</span><span class="sxs-lookup"><span data-stu-id="37f36-116">Set the `certificateValidationMode` attribute of the [\<certificateValidation>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) element to "Custom" to use this type.</span></span> <span data-ttu-id="37f36-117">Para obtener más información sobre cómo especificar el `type` atributo, vea [referencias de tipos personalizado](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="37f36-117">For more information about how to specify the `type` attribute, see [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="37f36-118">Opcional.</span><span class="sxs-lookup"><span data-stu-id="37f36-118">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="37f36-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="37f36-119">Child Elements</span></span>  
 <span data-ttu-id="37f36-120">Ninguna</span><span class="sxs-lookup"><span data-stu-id="37f36-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="37f36-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="37f36-121">Parent Elements</span></span>  
  
|<span data-ttu-id="37f36-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="37f36-122">Element</span></span>|<span data-ttu-id="37f36-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="37f36-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="37f36-124">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="37f36-124">\<certificateValidation></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|<span data-ttu-id="37f36-125">Controla la configuración que los controladores de token que se usan para validar los certificados.</span><span class="sxs-lookup"><span data-stu-id="37f36-125">Controls the settings that token handlers use to validate certificates.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="37f36-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="37f36-126">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="Custom"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine">  
    <certificateValidator type="MyNamespace.CustomValidator, MyAssembly" />    
</certificateValidation>        
```
