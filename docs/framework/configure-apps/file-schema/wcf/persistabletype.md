---
title: '&lt;Type con persistencia&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e5425fe6-523a-4076-aab4-2c2515b1d830
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 56443902885e191d93897096e55742f7665ba00a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="ltpersistabletypegt"></a><span data-ttu-id="75f3b-102">&lt;Type con persistencia&gt;</span><span class="sxs-lookup"><span data-stu-id="75f3b-102">&lt;persistableType&gt;</span></span>
<span data-ttu-id="75f3b-103">Especifica todos los tipos con persistencia.</span><span class="sxs-lookup"><span data-stu-id="75f3b-103">Specifies all the persistable types.</span></span>  
  
 <span data-ttu-id="75f3b-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="75f3b-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="75f3b-105">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="75f3b-105">\<comContracts></span></span>  
<span data-ttu-id="75f3b-106">\<comContract ></span><span class="sxs-lookup"><span data-stu-id="75f3b-106">\<comContract></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75f3b-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="75f3b-107">Syntax</span></span>  
  
```xml  
<comContracts>  
  <comContract>  
      <persistableTypes>  
         <persistableType id="string"  
            name="string">  
         </persistableType>  
      </persistableTypes>  
  </comContract>  
</comContracts>  
```  
  
## <a name="type"></a><span data-ttu-id="75f3b-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="75f3b-108">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="75f3b-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="75f3b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="75f3b-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="75f3b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="75f3b-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="75f3b-111">Attributes</span></span>  
  
|<span data-ttu-id="75f3b-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="75f3b-112">Attribute</span></span>|<span data-ttu-id="75f3b-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="75f3b-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="75f3b-114">id</span><span class="sxs-lookup"><span data-stu-id="75f3b-114">id</span></span>|<span data-ttu-id="75f3b-115">Un atributo necesario que contiene una cadena que especifica un identificador único para un tipo con persistencia.</span><span class="sxs-lookup"><span data-stu-id="75f3b-115">A required attribute that contains a string that specifies a unique identifier for a persistable type.</span></span>|  
|<span data-ttu-id="75f3b-116">name</span><span class="sxs-lookup"><span data-stu-id="75f3b-116">name</span></span>|<span data-ttu-id="75f3b-117">Un atributo opcional que contiene una cadena que especifica el nombre del tipo con persistencia.</span><span class="sxs-lookup"><span data-stu-id="75f3b-117">An optional attribute that contains a string that specifies the name of the persistable type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="75f3b-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="75f3b-118">Child Elements</span></span>  
 <span data-ttu-id="75f3b-119">Ninguna</span><span class="sxs-lookup"><span data-stu-id="75f3b-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="75f3b-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="75f3b-120">Parent Elements</span></span>  
  
|<span data-ttu-id="75f3b-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="75f3b-121">Element</span></span>|<span data-ttu-id="75f3b-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="75f3b-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="75f3b-123">\<persistableTypes ></span><span class="sxs-lookup"><span data-stu-id="75f3b-123">\<persistableTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md)|<span data-ttu-id="75f3b-124">Una colección de elementos de `persistableType`.</span><span class="sxs-lookup"><span data-stu-id="75f3b-124">A collection of `persistableType` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="75f3b-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="75f3b-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ComPersistableTypeElementCollection>  
 <xref:System.ServiceModel.Configuration.ComPersistableTypeElement>  
 [<span data-ttu-id="75f3b-126">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="75f3b-126">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)  
 [<span data-ttu-id="75f3b-127">Integración con aplicaciones COM +</span><span class="sxs-lookup"><span data-stu-id="75f3b-127">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)  
 [<span data-ttu-id="75f3b-128">Cómo: configurar el servicio COM +</span><span class="sxs-lookup"><span data-stu-id="75f3b-128">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
