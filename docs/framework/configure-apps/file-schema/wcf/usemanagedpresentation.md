---
title: <useManagedPresentation>
ms.date: 03/30/2017
ms.assetid: 17a0dd77-af54-41db-a9d0-4b17ff42878f
ms.openlocfilehash: bb2989ed52a88d805510d65e1dc1740df7bb55eb
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "73735942"
---
# \<useManagedPresentation>
<span data-ttu-id="a04fc-101">Elemento de enlace utilizado para comunicarse con un Servicio de token de seguridad de CardSpace que admite el perfil CardSpace de WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="a04fc-101">A binding element used to communicate with a CardSpace Security Token Service that supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="a04fc-102">Este elemento no tiene ningún atributo y está presente como modificador vacío.</span><span class="sxs-lookup"><span data-stu-id="a04fc-102">This element has no attribute and is present as an empty switch.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<useManagedPresentation>**  
  
## <a name="syntax"></a><span data-ttu-id="a04fc-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a04fc-103">Syntax</span></span>  
  
```xml  
<useManagedPresentation />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a04fc-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a04fc-104">Attributes and Elements</span></span>  
 <span data-ttu-id="a04fc-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a04fc-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a04fc-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="a04fc-106">Attributes</span></span>  
 <span data-ttu-id="a04fc-107">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a04fc-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a04fc-108">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a04fc-108">Child Elements</span></span>  
 <span data-ttu-id="a04fc-109">None</span><span class="sxs-lookup"><span data-stu-id="a04fc-109">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a04fc-110">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a04fc-110">Parent Elements</span></span>  
  
|<span data-ttu-id="a04fc-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="a04fc-111">Element</span></span>|<span data-ttu-id="a04fc-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="a04fc-112">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="a04fc-113">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="a04fc-113">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a04fc-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a04fc-114">Remarks</span></span>  
 <span data-ttu-id="a04fc-115">Un proveedor de identidad utiliza este elemento para expresar en su directiva el hecho de que admite el perfil CardSpace de WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="a04fc-115">This element is used by an identity provider to express in its policy the fact that it supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="a04fc-116">Los proveedores de identidad que publican este tipo de aserción de directiva deberían poder emitir tokens basados en ese perfil CardSpace.</span><span class="sxs-lookup"><span data-stu-id="a04fc-116">Identity providers that publish such a policy assertion should be able to issue tokens based on that CardSpace profile.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a04fc-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a04fc-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.UseManagedPresentationElement>
- <xref:System.ServiceModel.Channels.UseManagedPresentationBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="a04fc-118">Enlaces</span><span class="sxs-lookup"><span data-stu-id="a04fc-118">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="a04fc-119">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="a04fc-119">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="a04fc-120">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="a04fc-120">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
