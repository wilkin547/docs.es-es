---
description: 'Más información acerca de: <certificateValidator>'
title: <certificateValidator>
ms.date: 03/30/2017
ms.assetid: 86161897-c20f-4ad8-9d7f-050c247251bf
author: BrucePerlerMS
ms.openlocfilehash: 0b92eada916b239ca56342021bb958da6d02c2e7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802169"
---
# \<certificateValidator>

<span data-ttu-id="8a9ee-102">Especifica un tipo personalizado para la validación del certificado.</span><span class="sxs-lookup"><span data-stu-id="8a9ee-102">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="8a9ee-103">Este tipo solo se utiliza si el `certificateValidationMode` atributo del [\<certificateValidation>](certificatevalidation.md) elemento se establece en "Custom".</span><span class="sxs-lookup"><span data-stu-id="8a9ee-103">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element is set to "Custom".</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<certificateValidation>**](certificatevalidation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateValidator>**  
  
## <a name="syntax"></a><span data-ttu-id="8a9ee-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8a9ee-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8a9ee-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="8a9ee-105">Attributes and Elements</span></span>  

 <span data-ttu-id="8a9ee-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="8a9ee-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8a9ee-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="8a9ee-107">Attributes</span></span>  
  
|<span data-ttu-id="8a9ee-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="8a9ee-108">Attribute</span></span>|<span data-ttu-id="8a9ee-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="8a9ee-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8a9ee-110">type</span><span class="sxs-lookup"><span data-stu-id="8a9ee-110">type</span></span>|<span data-ttu-id="8a9ee-111">Especifica un tipo personalizado que deriva de la <xref:System.IdentityModel.Selectors.X509CertificateValidator> clase.</span><span class="sxs-lookup"><span data-stu-id="8a9ee-111">Specifies a custom type that derives from the <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span> <span data-ttu-id="8a9ee-112">Establezca el `certificateValidationMode` atributo del [\<certificateValidation>](certificatevalidation.md) elemento en "Custom" para usar este tipo.</span><span class="sxs-lookup"><span data-stu-id="8a9ee-112">Set the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element to "Custom" to use this type.</span></span> <span data-ttu-id="8a9ee-113">Para obtener más información sobre cómo especificar el `type` atributo, vea [referencias de tipo personalizado](../windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="8a9ee-113">For more information about how to specify the `type` attribute, see [Custom Type References](../windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="8a9ee-114">Opcional.</span><span class="sxs-lookup"><span data-stu-id="8a9ee-114">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8a9ee-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8a9ee-115">Child Elements</span></span>  

 <span data-ttu-id="8a9ee-116">None</span><span class="sxs-lookup"><span data-stu-id="8a9ee-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8a9ee-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8a9ee-117">Parent Elements</span></span>  
  
|<span data-ttu-id="8a9ee-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="8a9ee-118">Element</span></span>|<span data-ttu-id="8a9ee-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="8a9ee-119">Description</span></span>|  
|-------------|-----------------|  
|[\<certificateValidation>](certificatevalidation.md)|<span data-ttu-id="8a9ee-120">Controla la configuración que usan los controladores de token para validar certificados.</span><span class="sxs-lookup"><span data-stu-id="8a9ee-120">Controls the settings that token handlers use to validate certificates.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8a9ee-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8a9ee-121">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="Custom"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine">  
    <certificateValidator type="MyNamespace.CustomValidator, MyAssembly" />
</certificateValidation>
```
