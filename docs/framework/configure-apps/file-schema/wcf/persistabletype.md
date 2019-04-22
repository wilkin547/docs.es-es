---
title: <persistableType>
ms.date: 03/30/2017
ms.assetid: e5425fe6-523a-4076-aab4-2c2515b1d830
ms.openlocfilehash: 939a29e90ee21e94ccb78842d6f7224e9a6288d0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59083743"
---
# <a name="persistabletype"></a><span data-ttu-id="d58d4-101">\<persistableType></span><span class="sxs-lookup"><span data-stu-id="d58d4-101">\<persistableType></span></span>
<span data-ttu-id="d58d4-102">Especifica todos los tipos con persistencia.</span><span class="sxs-lookup"><span data-stu-id="d58d4-102">Specifies all the persistable types.</span></span>  
  
 <span data-ttu-id="d58d4-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d58d4-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="d58d4-104">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="d58d4-104">\<comContracts></span></span>  
<span data-ttu-id="d58d4-105">\<comContract></span><span class="sxs-lookup"><span data-stu-id="d58d4-105">\<comContract></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d58d4-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d58d4-106">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="d58d4-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="d58d4-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d58d4-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d58d4-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d58d4-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d58d4-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d58d4-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="d58d4-110">Attributes</span></span>  
  
|<span data-ttu-id="d58d4-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="d58d4-111">Attribute</span></span>|<span data-ttu-id="d58d4-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="d58d4-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d58d4-113">id</span><span class="sxs-lookup"><span data-stu-id="d58d4-113">id</span></span>|<span data-ttu-id="d58d4-114">Un atributo necesario que contiene una cadena que especifica un identificador único para un tipo con persistencia.</span><span class="sxs-lookup"><span data-stu-id="d58d4-114">A required attribute that contains a string that specifies a unique identifier for a persistable type.</span></span>|  
|<span data-ttu-id="d58d4-115">name</span><span class="sxs-lookup"><span data-stu-id="d58d4-115">name</span></span>|<span data-ttu-id="d58d4-116">Un atributo opcional que contiene una cadena que especifica el nombre del tipo con persistencia.</span><span class="sxs-lookup"><span data-stu-id="d58d4-116">An optional attribute that contains a string that specifies the name of the persistable type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d58d4-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d58d4-117">Child Elements</span></span>  
 <span data-ttu-id="d58d4-118">Ninguna</span><span class="sxs-lookup"><span data-stu-id="d58d4-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d58d4-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d58d4-119">Parent Elements</span></span>  
  
|<span data-ttu-id="d58d4-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="d58d4-120">Element</span></span>|<span data-ttu-id="d58d4-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="d58d4-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d58d4-122">\<persistableTypes></span><span class="sxs-lookup"><span data-stu-id="d58d4-122">\<persistableTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md)|<span data-ttu-id="d58d4-123">Una colección de elementos de `persistableType`.</span><span class="sxs-lookup"><span data-stu-id="d58d4-123">A collection of `persistableType` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d58d4-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="d58d4-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComPersistableTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ComPersistableTypeElement>
- [<span data-ttu-id="d58d4-125">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="d58d4-125">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)
- [<span data-ttu-id="d58d4-126">Integración en aplicaciones COM+</span><span class="sxs-lookup"><span data-stu-id="d58d4-126">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="d58d4-127">Cómo: Configurar el servicio COM +</span><span class="sxs-lookup"><span data-stu-id="d58d4-127">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
