---
title: <useManagedPresentation>
ms.date: 03/30/2017
ms.assetid: 17a0dd77-af54-41db-a9d0-4b17ff42878f
ms.openlocfilehash: 1134c4d5f18f60bb2986f4239a788b836fa9113e
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55287253"
---
# <a name="usemanagedpresentation"></a><span data-ttu-id="11514-101">\<useManagedPresentation></span><span class="sxs-lookup"><span data-stu-id="11514-101">\<useManagedPresentation></span></span>
<span data-ttu-id="11514-102">Elemento de enlace utilizado para comunicarse con un Servicio de token de seguridad de CardSpace que admite el perfil CardSpace de WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="11514-102">A binding element used to communicate with a CardSpace Security Token Service that supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="11514-103">Este elemento no tiene ningún atributo y está presente como modificador vacío.</span><span class="sxs-lookup"><span data-stu-id="11514-103">This element has no attribute and is present as an empty switch.</span></span>  
  
 <span data-ttu-id="11514-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="11514-104">\<system.serviceModel></span></span>  
<span data-ttu-id="11514-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="11514-105">\<bindings></span></span>  
<span data-ttu-id="11514-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="11514-106">\<customBinding></span></span>  
<span data-ttu-id="11514-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="11514-107">\<binding></span></span>  
<span data-ttu-id="11514-108">\<useManagedPresentation></span><span class="sxs-lookup"><span data-stu-id="11514-108">\<useManagedPresentation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11514-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="11514-109">Syntax</span></span>  
  
```xml  
<useManagedPresentation />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="11514-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="11514-110">Attributes and Elements</span></span>  
 <span data-ttu-id="11514-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="11514-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="11514-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="11514-112">Attributes</span></span>  
 <span data-ttu-id="11514-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="11514-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="11514-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="11514-114">Child Elements</span></span>  
 <span data-ttu-id="11514-115">Ninguna</span><span class="sxs-lookup"><span data-stu-id="11514-115">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="11514-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="11514-116">Parent Elements</span></span>  
  
|<span data-ttu-id="11514-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="11514-117">Element</span></span>|<span data-ttu-id="11514-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="11514-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="11514-119">\<binding></span><span class="sxs-lookup"><span data-stu-id="11514-119">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="11514-120">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="11514-120">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="11514-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="11514-121">Remarks</span></span>  
 <span data-ttu-id="11514-122">Un proveedor de identidad utiliza este elemento para expresar en su directiva el hecho de que admite el perfil CardSpace de WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="11514-122">This element is used by an identity provider to express in its policy the fact that it supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="11514-123">Los proveedores de identidad que publican este tipo de aserción de directiva deberían poder emitir tokens basados en ese perfil CardSpace.</span><span class="sxs-lookup"><span data-stu-id="11514-123">Identity providers that publish such a policy assertion should be able to issue tokens based on that CardSpace profile.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11514-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="11514-124">See also</span></span>
- <xref:System.ServiceModel.Configuration.UseManagedPresentationElement>
- <xref:System.ServiceModel.Channels.UseManagedPresentationBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="11514-125">Enlaces</span><span class="sxs-lookup"><span data-stu-id="11514-125">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="11514-126">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="11514-126">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="11514-127">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="11514-127">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="11514-128">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="11514-128">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
