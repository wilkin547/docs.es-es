---
title: <useManagedPresentation>
ms.date: 03/30/2017
ms.assetid: 17a0dd77-af54-41db-a9d0-4b17ff42878f
ms.openlocfilehash: e67cc316b8747ee785055ceb4f954988fa82a44c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940610"
---
# <a name="usemanagedpresentation"></a><span data-ttu-id="83ec6-101">\<useManagedPresentation></span><span class="sxs-lookup"><span data-stu-id="83ec6-101">\<useManagedPresentation></span></span>
<span data-ttu-id="83ec6-102">Elemento de enlace utilizado para comunicarse con un Servicio de token de seguridad de CardSpace que admite el perfil CardSpace de WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="83ec6-102">A binding element used to communicate with a CardSpace Security Token Service that supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="83ec6-103">Este elemento no tiene ningún atributo y está presente como modificador vacío.</span><span class="sxs-lookup"><span data-stu-id="83ec6-103">This element has no attribute and is present as an empty switch.</span></span>  
  
 <span data-ttu-id="83ec6-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="83ec6-104">\<system.serviceModel></span></span>  
<span data-ttu-id="83ec6-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="83ec6-105">\<bindings></span></span>  
<span data-ttu-id="83ec6-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="83ec6-106">\<customBinding></span></span>  
<span data-ttu-id="83ec6-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="83ec6-107">\<binding></span></span>  
<span data-ttu-id="83ec6-108">\<useManagedPresentation></span><span class="sxs-lookup"><span data-stu-id="83ec6-108">\<useManagedPresentation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83ec6-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="83ec6-109">Syntax</span></span>  
  
```xml  
<useManagedPresentation />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="83ec6-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="83ec6-110">Attributes and Elements</span></span>  
 <span data-ttu-id="83ec6-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="83ec6-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="83ec6-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="83ec6-112">Attributes</span></span>  
 <span data-ttu-id="83ec6-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="83ec6-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="83ec6-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="83ec6-114">Child Elements</span></span>  
 <span data-ttu-id="83ec6-115">None</span><span class="sxs-lookup"><span data-stu-id="83ec6-115">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="83ec6-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="83ec6-116">Parent Elements</span></span>  
  
|<span data-ttu-id="83ec6-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="83ec6-117">Element</span></span>|<span data-ttu-id="83ec6-118">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="83ec6-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="83ec6-119">\<binding></span><span class="sxs-lookup"><span data-stu-id="83ec6-119">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="83ec6-120">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="83ec6-120">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="83ec6-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="83ec6-121">Remarks</span></span>  
 <span data-ttu-id="83ec6-122">Un proveedor de identidad utiliza este elemento para expresar en su directiva el hecho de que admite el perfil CardSpace de WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="83ec6-122">This element is used by an identity provider to express in its policy the fact that it supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="83ec6-123">Los proveedores de identidad que publican este tipo de aserción de directiva deberían poder emitir tokens basados en ese perfil CardSpace.</span><span class="sxs-lookup"><span data-stu-id="83ec6-123">Identity providers that publish such a policy assertion should be able to issue tokens based on that CardSpace profile.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83ec6-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="83ec6-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.UseManagedPresentationElement>
- <xref:System.ServiceModel.Channels.UseManagedPresentationBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="83ec6-125">Enlaces</span><span class="sxs-lookup"><span data-stu-id="83ec6-125">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="83ec6-126">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="83ec6-126">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="83ec6-127">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="83ec6-127">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="83ec6-128">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="83ec6-128">\<customBinding></span></span>](custombinding.md)
