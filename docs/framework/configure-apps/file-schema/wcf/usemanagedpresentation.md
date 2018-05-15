---
title: '&lt;useManagedPresentation&gt;'
ms.date: 03/30/2017
ms.assetid: 17a0dd77-af54-41db-a9d0-4b17ff42878f
ms.openlocfilehash: 35af7f5e10594617807384c20ab706ad675d11ef
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltusemanagedpresentationgt"></a><span data-ttu-id="75143-102">&lt;useManagedPresentation&gt;</span><span class="sxs-lookup"><span data-stu-id="75143-102">&lt;useManagedPresentation&gt;</span></span>
<span data-ttu-id="75143-103">Elemento de enlace utilizado para comunicarse con un Servicio de token de seguridad de CardSpace que admite el perfil CardSpace de WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="75143-103">A binding element used to communicate with a CardSpace Security Token Service that supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="75143-104">Este elemento no tiene ningún atributo y está presente como modificador vacío.</span><span class="sxs-lookup"><span data-stu-id="75143-104">This element has no attribute and is present as an empty switch.</span></span>  
  
 <span data-ttu-id="75143-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="75143-105">\<system.serviceModel></span></span>  
<span data-ttu-id="75143-106">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="75143-106">\<bindings></span></span>  
<span data-ttu-id="75143-107">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="75143-107">\<customBinding></span></span>  
<span data-ttu-id="75143-108">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="75143-108">\<binding></span></span>  
<span data-ttu-id="75143-109">\<useManagedPresentation ></span><span class="sxs-lookup"><span data-stu-id="75143-109">\<useManagedPresentation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75143-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="75143-110">Syntax</span></span>  
  
```xml  
<useManagedPresentation/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="75143-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="75143-111">Attributes and Elements</span></span>  
 <span data-ttu-id="75143-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="75143-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="75143-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="75143-113">Attributes</span></span>  
 <span data-ttu-id="75143-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="75143-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="75143-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="75143-115">Child Elements</span></span>  
 <span data-ttu-id="75143-116">Ninguna</span><span class="sxs-lookup"><span data-stu-id="75143-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="75143-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="75143-117">Parent Elements</span></span>  
  
|<span data-ttu-id="75143-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="75143-118">Element</span></span>|<span data-ttu-id="75143-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="75143-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="75143-120">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="75143-120">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="75143-121">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="75143-121">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="75143-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="75143-122">Remarks</span></span>  
 <span data-ttu-id="75143-123">Un proveedor de identidad utiliza este elemento para expresar en su directiva el hecho de que admite el perfil CardSpace de WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="75143-123">This element is used by an identity provider to express in its policy the fact that it supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="75143-124">Los proveedores de identidad que publican este tipo de aserción de directiva deberían poder emitir tokens basados en ese perfil CardSpace.</span><span class="sxs-lookup"><span data-stu-id="75143-124">Identity providers that publish such a policy assertion should be able to issue tokens based on that CardSpace profile.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75143-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="75143-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.UseManagedPresentationElement>  
 <xref:System.ServiceModel.Channels.UseManagedPresentationBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="75143-126">Enlaces</span><span class="sxs-lookup"><span data-stu-id="75143-126">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="75143-127">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="75143-127">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="75143-128">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="75143-128">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="75143-129">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="75143-129">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
