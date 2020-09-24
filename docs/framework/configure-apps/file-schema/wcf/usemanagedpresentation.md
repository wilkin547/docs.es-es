---
title: <useManagedPresentation>
ms.date: 03/30/2017
ms.assetid: 17a0dd77-af54-41db-a9d0-4b17ff42878f
ms.openlocfilehash: 86a6f975b05133d5f9f21fcfb82ef4c23d2ffaba
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148817"
---
# \<useManagedPresentation>

<span data-ttu-id="ea67f-101">Elemento de enlace utilizado para comunicarse con un Servicio de token de seguridad de CardSpace que admite el perfil CardSpace de WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="ea67f-101">A binding element used to communicate with a CardSpace Security Token Service that supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="ea67f-102">Este elemento no tiene ningún atributo y está presente como modificador vacío.</span><span class="sxs-lookup"><span data-stu-id="ea67f-102">This element has no attribute and is present as an empty switch.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<useManagedPresentation>**  
  
## <a name="syntax"></a><span data-ttu-id="ea67f-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ea67f-103">Syntax</span></span>  
  
```xml  
<useManagedPresentation />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ea67f-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ea67f-104">Attributes and Elements</span></span>  

 <span data-ttu-id="ea67f-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ea67f-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ea67f-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="ea67f-106">Attributes</span></span>  

 <span data-ttu-id="ea67f-107">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="ea67f-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ea67f-108">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ea67f-108">Child Elements</span></span>  

 <span data-ttu-id="ea67f-109">None</span><span class="sxs-lookup"><span data-stu-id="ea67f-109">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ea67f-110">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ea67f-110">Parent Elements</span></span>  
  
|<span data-ttu-id="ea67f-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="ea67f-111">Element</span></span>|<span data-ttu-id="ea67f-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="ea67f-112">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="ea67f-113">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="ea67f-113">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ea67f-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ea67f-114">Remarks</span></span>  

 <span data-ttu-id="ea67f-115">Un proveedor de identidad utiliza este elemento para expresar en su directiva el hecho de que admite el perfil CardSpace de WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="ea67f-115">This element is used by an identity provider to express in its policy the fact that it supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="ea67f-116">Los proveedores de identidad que publican este tipo de aserción de directiva deberían poder emitir tokens basados en ese perfil CardSpace.</span><span class="sxs-lookup"><span data-stu-id="ea67f-116">Identity providers that publish such a policy assertion should be able to issue tokens based on that CardSpace profile.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea67f-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="ea67f-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.UseManagedPresentationElement>
- <xref:System.ServiceModel.Channels.UseManagedPresentationBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="ea67f-118">Enlaces</span><span class="sxs-lookup"><span data-stu-id="ea67f-118">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="ea67f-119">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="ea67f-119">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="ea67f-120">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="ea67f-120">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
