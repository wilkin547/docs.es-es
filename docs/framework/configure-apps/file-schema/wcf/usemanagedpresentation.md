---
title: <useManagedPresentation>
ms.date: 03/30/2017
ms.assetid: 17a0dd77-af54-41db-a9d0-4b17ff42878f
ms.openlocfilehash: c410967e84c9318d21ce0b3072d08b026a37b190
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399210"
---
# <a name="usemanagedpresentation"></a><span data-ttu-id="15637-101">\<useManagedPresentation></span><span class="sxs-lookup"><span data-stu-id="15637-101">\<useManagedPresentation></span></span>
<span data-ttu-id="15637-102">Elemento de enlace utilizado para comunicarse con un Servicio de token de seguridad de CardSpace que admite el perfil CardSpace de WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="15637-102">A binding element used to communicate with a CardSpace Security Token Service that supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="15637-103">Este elemento no tiene ningún atributo y está presente como modificador vacío.</span><span class="sxs-lookup"><span data-stu-id="15637-103">This element has no attribute and is present as an empty switch.</span></span>  
  
<span data-ttu-id="15637-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="15637-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="15637-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="15637-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="15637-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de enlaces**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="15637-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="15637-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="15637-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="15637-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de enlace**</span><span class="sxs-lookup"><span data-stu-id="15637-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="15637-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> useManagedPresentation**</span><span class="sxs-lookup"><span data-stu-id="15637-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<useManagedPresentation>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15637-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="15637-110">Syntax</span></span>  
  
```xml  
<useManagedPresentation />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="15637-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="15637-111">Attributes and Elements</span></span>  
 <span data-ttu-id="15637-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="15637-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="15637-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="15637-113">Attributes</span></span>  
 <span data-ttu-id="15637-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="15637-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="15637-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="15637-115">Child Elements</span></span>  
 <span data-ttu-id="15637-116">None</span><span class="sxs-lookup"><span data-stu-id="15637-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="15637-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="15637-117">Parent Elements</span></span>  
  
|<span data-ttu-id="15637-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="15637-118">Element</span></span>|<span data-ttu-id="15637-119">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="15637-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="15637-120">\<binding></span><span class="sxs-lookup"><span data-stu-id="15637-120">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="15637-121">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="15637-121">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="15637-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="15637-122">Remarks</span></span>  
 <span data-ttu-id="15637-123">Un proveedor de identidad utiliza este elemento para expresar en su directiva el hecho de que admite el perfil CardSpace de WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="15637-123">This element is used by an identity provider to express in its policy the fact that it supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="15637-124">Los proveedores de identidad que publican este tipo de aserción de directiva deberían poder emitir tokens basados en ese perfil CardSpace.</span><span class="sxs-lookup"><span data-stu-id="15637-124">Identity providers that publish such a policy assertion should be able to issue tokens based on that CardSpace profile.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15637-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="15637-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.UseManagedPresentationElement>
- <xref:System.ServiceModel.Channels.UseManagedPresentationBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="15637-126">Enlaces</span><span class="sxs-lookup"><span data-stu-id="15637-126">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="15637-127">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="15637-127">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="15637-128">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="15637-128">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="15637-129">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="15637-129">\<customBinding></span></span>](custombinding.md)
