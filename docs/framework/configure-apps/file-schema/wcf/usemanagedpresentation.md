---
title: <useManagedPresentation>
ms.date: 03/30/2017
ms.assetid: 17a0dd77-af54-41db-a9d0-4b17ff42878f
ms.openlocfilehash: eedf0ce6cf75b8fb56daf98f2005e66162ce10d8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59155660"
---
# <a name="usemanagedpresentation"></a><span data-ttu-id="852e4-101">\<useManagedPresentation></span><span class="sxs-lookup"><span data-stu-id="852e4-101">\<useManagedPresentation></span></span>
<span data-ttu-id="852e4-102">Elemento de enlace utilizado para comunicarse con un Servicio de token de seguridad de CardSpace que admite el perfil CardSpace de WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="852e4-102">A binding element used to communicate with a CardSpace Security Token Service that supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="852e4-103">Este elemento no tiene ningún atributo y está presente como modificador vacío.</span><span class="sxs-lookup"><span data-stu-id="852e4-103">This element has no attribute and is present as an empty switch.</span></span>  
  
 <span data-ttu-id="852e4-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="852e4-104">\<system.serviceModel></span></span>  
<span data-ttu-id="852e4-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="852e4-105">\<bindings></span></span>  
<span data-ttu-id="852e4-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="852e4-106">\<customBinding></span></span>  
<span data-ttu-id="852e4-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="852e4-107">\<binding></span></span>  
<span data-ttu-id="852e4-108">\<useManagedPresentation></span><span class="sxs-lookup"><span data-stu-id="852e4-108">\<useManagedPresentation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="852e4-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="852e4-109">Syntax</span></span>  
  
```xml  
<useManagedPresentation />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="852e4-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="852e4-110">Attributes and Elements</span></span>  
 <span data-ttu-id="852e4-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="852e4-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="852e4-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="852e4-112">Attributes</span></span>  
 <span data-ttu-id="852e4-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="852e4-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="852e4-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="852e4-114">Child Elements</span></span>  
 <span data-ttu-id="852e4-115">Ninguna</span><span class="sxs-lookup"><span data-stu-id="852e4-115">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="852e4-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="852e4-116">Parent Elements</span></span>  
  
|<span data-ttu-id="852e4-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="852e4-117">Element</span></span>|<span data-ttu-id="852e4-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="852e4-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="852e4-119">\<binding></span><span class="sxs-lookup"><span data-stu-id="852e4-119">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="852e4-120">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="852e4-120">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="852e4-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="852e4-121">Remarks</span></span>  
 <span data-ttu-id="852e4-122">Un proveedor de identidad utiliza este elemento para expresar en su directiva el hecho de que admite el perfil CardSpace de WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="852e4-122">This element is used by an identity provider to express in its policy the fact that it supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="852e4-123">Los proveedores de identidad que publican este tipo de aserción de directiva deberían poder emitir tokens basados en ese perfil CardSpace.</span><span class="sxs-lookup"><span data-stu-id="852e4-123">Identity providers that publish such a policy assertion should be able to issue tokens based on that CardSpace profile.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="852e4-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="852e4-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.UseManagedPresentationElement>
- <xref:System.ServiceModel.Channels.UseManagedPresentationBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="852e4-125">Enlaces</span><span class="sxs-lookup"><span data-stu-id="852e4-125">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="852e4-126">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="852e4-126">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="852e4-127">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="852e4-127">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="852e4-128">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="852e4-128">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
