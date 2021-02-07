---
description: 'Más información acerca de: <useManagedPresentation>'
title: <useManagedPresentation>
ms.date: 03/30/2017
ms.assetid: 17a0dd77-af54-41db-a9d0-4b17ff42878f
ms.openlocfilehash: 9203daedcc0553c7a1308b2763b9e818ca6560c1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99749043"
---
# \<useManagedPresentation>

<span data-ttu-id="ffd95-102">Elemento de enlace utilizado para comunicarse con un Servicio de token de seguridad de CardSpace que admite el perfil CardSpace de WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="ffd95-102">A binding element used to communicate with a CardSpace Security Token Service that supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="ffd95-103">Este elemento no tiene ningún atributo y está presente como modificador vacío.</span><span class="sxs-lookup"><span data-stu-id="ffd95-103">This element has no attribute and is present as an empty switch.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<useManagedPresentation>**  
  
## <a name="syntax"></a><span data-ttu-id="ffd95-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ffd95-104">Syntax</span></span>  
  
```xml  
<useManagedPresentation />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ffd95-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ffd95-105">Attributes and Elements</span></span>  

 <span data-ttu-id="ffd95-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ffd95-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ffd95-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="ffd95-107">Attributes</span></span>  

 <span data-ttu-id="ffd95-108">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="ffd95-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ffd95-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ffd95-109">Child Elements</span></span>  

 <span data-ttu-id="ffd95-110">None</span><span class="sxs-lookup"><span data-stu-id="ffd95-110">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ffd95-111">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ffd95-111">Parent Elements</span></span>  
  
|<span data-ttu-id="ffd95-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="ffd95-112">Element</span></span>|<span data-ttu-id="ffd95-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="ffd95-113">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="ffd95-114">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="ffd95-114">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ffd95-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ffd95-115">Remarks</span></span>  

 <span data-ttu-id="ffd95-116">Un proveedor de identidad utiliza este elemento para expresar en su directiva el hecho de que admite el perfil CardSpace de WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="ffd95-116">This element is used by an identity provider to express in its policy the fact that it supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="ffd95-117">Los proveedores de identidad que publican este tipo de aserción de directiva deberían poder emitir tokens basados en ese perfil CardSpace.</span><span class="sxs-lookup"><span data-stu-id="ffd95-117">Identity providers that publish such a policy assertion should be able to issue tokens based on that CardSpace profile.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffd95-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="ffd95-118">See also</span></span>

- <xref:System.ServiceModel.Configuration.UseManagedPresentationElement>
- <xref:System.ServiceModel.Channels.UseManagedPresentationBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="ffd95-119">Enlaces</span><span class="sxs-lookup"><span data-stu-id="ffd95-119">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="ffd95-120">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="ffd95-120">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="ffd95-121">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="ffd95-121">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
