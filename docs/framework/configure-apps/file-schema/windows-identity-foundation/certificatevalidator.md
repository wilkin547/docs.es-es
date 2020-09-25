---
title: <certificateValidator>
ms.date: 03/30/2017
ms.assetid: 86161897-c20f-4ad8-9d7f-050c247251bf
author: BrucePerlerMS
ms.openlocfilehash: 8476600769b6099bb885566de4c908c78a2dbbda
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201384"
---
# \<certificateValidator>

<span data-ttu-id="7dd2f-101">Especifica un tipo personalizado para la validación del certificado.</span><span class="sxs-lookup"><span data-stu-id="7dd2f-101">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="7dd2f-102">Este tipo solo se utiliza si el `certificateValidationMode` atributo del [\<certificateValidation>](certificatevalidation.md) elemento se establece en "Custom".</span><span class="sxs-lookup"><span data-stu-id="7dd2f-102">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element is set to "Custom".</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<certificateValidation>**](certificatevalidation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateValidator>**  
  
## <a name="syntax"></a><span data-ttu-id="7dd2f-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7dd2f-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7dd2f-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="7dd2f-104">Attributes and Elements</span></span>  

 <span data-ttu-id="7dd2f-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="7dd2f-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7dd2f-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="7dd2f-106">Attributes</span></span>  
  
|<span data-ttu-id="7dd2f-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="7dd2f-107">Attribute</span></span>|<span data-ttu-id="7dd2f-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="7dd2f-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7dd2f-109">type</span><span class="sxs-lookup"><span data-stu-id="7dd2f-109">type</span></span>|<span data-ttu-id="7dd2f-110">Especifica un tipo personalizado que deriva de la <xref:System.IdentityModel.Selectors.X509CertificateValidator> clase.</span><span class="sxs-lookup"><span data-stu-id="7dd2f-110">Specifies a custom type that derives from the <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span> <span data-ttu-id="7dd2f-111">Establezca el `certificateValidationMode` atributo del [\<certificateValidation>](certificatevalidation.md) elemento en "Custom" para usar este tipo.</span><span class="sxs-lookup"><span data-stu-id="7dd2f-111">Set the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element to "Custom" to use this type.</span></span> <span data-ttu-id="7dd2f-112">Para obtener más información sobre cómo especificar el `type` atributo, vea [referencias de tipo personalizado](../windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="7dd2f-112">For more information about how to specify the `type` attribute, see [Custom Type References](../windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="7dd2f-113">Opcional.</span><span class="sxs-lookup"><span data-stu-id="7dd2f-113">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7dd2f-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="7dd2f-114">Child Elements</span></span>  

 <span data-ttu-id="7dd2f-115">None</span><span class="sxs-lookup"><span data-stu-id="7dd2f-115">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7dd2f-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="7dd2f-116">Parent Elements</span></span>  
  
|<span data-ttu-id="7dd2f-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="7dd2f-117">Element</span></span>|<span data-ttu-id="7dd2f-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="7dd2f-118">Description</span></span>|  
|-------------|-----------------|  
|[\<certificateValidation>](certificatevalidation.md)|<span data-ttu-id="7dd2f-119">Controla la configuración que usan los controladores de token para validar certificados.</span><span class="sxs-lookup"><span data-stu-id="7dd2f-119">Controls the settings that token handlers use to validate certificates.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7dd2f-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7dd2f-120">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="Custom"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine">  
    <certificateValidator type="MyNamespace.CustomValidator, MyAssembly" />
</certificateValidation>
```
