---
title: '&lt;persistableType&gt;'
ms.date: 03/30/2017
ms.assetid: e5425fe6-523a-4076-aab4-2c2515b1d830
ms.openlocfilehash: 92c59b3804e22c62340acccc1e12e594203c8e8b
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145424"
---
# <a name="ltpersistabletypegt"></a><span data-ttu-id="ab570-102">&lt;persistableType&gt;</span><span class="sxs-lookup"><span data-stu-id="ab570-102">&lt;persistableType&gt;</span></span>
<span data-ttu-id="ab570-103">Especifica todos los tipos con persistencia.</span><span class="sxs-lookup"><span data-stu-id="ab570-103">Specifies all the persistable types.</span></span>  
  
 <span data-ttu-id="ab570-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="ab570-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="ab570-105">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="ab570-105">\<comContracts></span></span>  
<span data-ttu-id="ab570-106">\<comContract ></span><span class="sxs-lookup"><span data-stu-id="ab570-106">\<comContract></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab570-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ab570-107">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="ab570-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="ab570-108">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ab570-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ab570-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ab570-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ab570-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ab570-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="ab570-111">Attributes</span></span>  
  
|<span data-ttu-id="ab570-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="ab570-112">Attribute</span></span>|<span data-ttu-id="ab570-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="ab570-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ab570-114">id</span><span class="sxs-lookup"><span data-stu-id="ab570-114">id</span></span>|<span data-ttu-id="ab570-115">Un atributo necesario que contiene una cadena que especifica un identificador único para un tipo con persistencia.</span><span class="sxs-lookup"><span data-stu-id="ab570-115">A required attribute that contains a string that specifies a unique identifier for a persistable type.</span></span>|  
|<span data-ttu-id="ab570-116">name</span><span class="sxs-lookup"><span data-stu-id="ab570-116">name</span></span>|<span data-ttu-id="ab570-117">Un atributo opcional que contiene una cadena que especifica el nombre del tipo con persistencia.</span><span class="sxs-lookup"><span data-stu-id="ab570-117">An optional attribute that contains a string that specifies the name of the persistable type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ab570-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ab570-118">Child Elements</span></span>  
 <span data-ttu-id="ab570-119">Ninguna</span><span class="sxs-lookup"><span data-stu-id="ab570-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ab570-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ab570-120">Parent Elements</span></span>  
  
|<span data-ttu-id="ab570-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="ab570-121">Element</span></span>|<span data-ttu-id="ab570-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="ab570-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ab570-123">\<persistableTypes ></span><span class="sxs-lookup"><span data-stu-id="ab570-123">\<persistableTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md)|<span data-ttu-id="ab570-124">Una colección de elementos de `persistableType`.</span><span class="sxs-lookup"><span data-stu-id="ab570-124">A collection of `persistableType` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ab570-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="ab570-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ComPersistableTypeElementCollection>  
 <xref:System.ServiceModel.Configuration.ComPersistableTypeElement>  
 [<span data-ttu-id="ab570-126">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="ab570-126">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)  
 [<span data-ttu-id="ab570-127">Integración en aplicaciones COM+</span><span class="sxs-lookup"><span data-stu-id="ab570-127">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)  
 [<span data-ttu-id="ab570-128">Cómo: Configurar el servicio COM +</span><span class="sxs-lookup"><span data-stu-id="ab570-128">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
