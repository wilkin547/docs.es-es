---
title: <persistableType>
ms.date: 03/30/2017
ms.assetid: e5425fe6-523a-4076-aab4-2c2515b1d830
ms.openlocfilehash: 328caaefe0cc24da45b460cab0a672dc8a6ccce1
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855073"
---
# <a name="persistabletype"></a><span data-ttu-id="c4b6d-101">\<persistableType></span><span class="sxs-lookup"><span data-stu-id="c4b6d-101">\<persistableType></span></span>
<span data-ttu-id="c4b6d-102">Especifica todos los tipos con persistencia.</span><span class="sxs-lookup"><span data-stu-id="c4b6d-102">Specifies all the persistable types.</span></span>  
  
<span data-ttu-id="c4b6d-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c4b6d-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c4b6d-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="c4b6d-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="c4b6d-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de compactos**](comcontracts.md)</span><span class="sxs-lookup"><span data-stu-id="c4b6d-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContracts>**](comcontracts.md)</span></span>\
<span data-ttu-id="c4b6d-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> compactos**](comcontract.md)</span><span class="sxs-lookup"><span data-stu-id="c4b6d-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContract>**](comcontract.md)</span></span>\
<span data-ttu-id="c4b6d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> persistableTypes**](persistabletypes.md)</span><span class="sxs-lookup"><span data-stu-id="c4b6d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<persistableTypes>**](persistabletypes.md)</span></span>\
<span data-ttu-id="c4b6d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> persistableType**</span><span class="sxs-lookup"><span data-stu-id="c4b6d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<persistableType>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4b6d-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c4b6d-109">Syntax</span></span>  
  
```xml  
<comContracts>
  <comContract>
    <persistableTypes>
      <persistableType id="String"
                       name="String">
      </persistableType>
    </persistableTypes>
  </comContract>
</comContracts>
```  
  
## <a name="type"></a><span data-ttu-id="c4b6d-110">Type</span><span class="sxs-lookup"><span data-stu-id="c4b6d-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c4b6d-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c4b6d-111">Attributes and Elements</span></span>  
 <span data-ttu-id="c4b6d-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c4b6d-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c4b6d-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="c4b6d-113">Attributes</span></span>  
  
|<span data-ttu-id="c4b6d-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="c4b6d-114">Attribute</span></span>|<span data-ttu-id="c4b6d-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="c4b6d-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c4b6d-116">id</span><span class="sxs-lookup"><span data-stu-id="c4b6d-116">id</span></span>|<span data-ttu-id="c4b6d-117">Un atributo necesario que contiene una cadena que especifica un identificador único para un tipo con persistencia.</span><span class="sxs-lookup"><span data-stu-id="c4b6d-117">A required attribute that contains a string that specifies a unique identifier for a persistable type.</span></span>|  
|<span data-ttu-id="c4b6d-118">name</span><span class="sxs-lookup"><span data-stu-id="c4b6d-118">name</span></span>|<span data-ttu-id="c4b6d-119">Un atributo opcional que contiene una cadena que especifica el nombre del tipo con persistencia.</span><span class="sxs-lookup"><span data-stu-id="c4b6d-119">An optional attribute that contains a string that specifies the name of the persistable type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c4b6d-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c4b6d-120">Child Elements</span></span>  
 <span data-ttu-id="c4b6d-121">None</span><span class="sxs-lookup"><span data-stu-id="c4b6d-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c4b6d-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c4b6d-122">Parent Elements</span></span>  
  
|<span data-ttu-id="c4b6d-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="c4b6d-123">Element</span></span>|<span data-ttu-id="c4b6d-124">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="c4b6d-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c4b6d-125">\<persistableTypes></span><span class="sxs-lookup"><span data-stu-id="c4b6d-125">\<persistableTypes></span></span>](persistabletypes.md)|<span data-ttu-id="c4b6d-126">Una colección de elementos de `persistableType`.</span><span class="sxs-lookup"><span data-stu-id="c4b6d-126">A collection of `persistableType` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c4b6d-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="c4b6d-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComPersistableTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ComPersistableTypeElement>
- [<span data-ttu-id="c4b6d-128">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="c4b6d-128">\<comContracts></span></span>](comcontracts.md)
- [<span data-ttu-id="c4b6d-129">Integración en aplicaciones COM+</span><span class="sxs-lookup"><span data-stu-id="c4b6d-129">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="c4b6d-130">Procedimientos: Configurar el servicio COM+</span><span class="sxs-lookup"><span data-stu-id="c4b6d-130">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
