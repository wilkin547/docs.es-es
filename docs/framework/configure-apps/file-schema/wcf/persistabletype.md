---
title: <persistableType>
ms.date: 03/30/2017
ms.assetid: e5425fe6-523a-4076-aab4-2c2515b1d830
ms.openlocfilehash: fcfd338e289b5151688724f0e84b6878707d32be
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933835"
---
# <a name="persistabletype"></a><span data-ttu-id="2087c-101">\<persistableType></span><span class="sxs-lookup"><span data-stu-id="2087c-101">\<persistableType></span></span>
<span data-ttu-id="2087c-102">Especifica todos los tipos con persistencia.</span><span class="sxs-lookup"><span data-stu-id="2087c-102">Specifies all the persistable types.</span></span>  
  
 <span data-ttu-id="2087c-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="2087c-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="2087c-104">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="2087c-104">\<comContracts></span></span>  
<span data-ttu-id="2087c-105">\<comContract></span><span class="sxs-lookup"><span data-stu-id="2087c-105">\<comContract></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2087c-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2087c-106">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="2087c-107">Type</span><span class="sxs-lookup"><span data-stu-id="2087c-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2087c-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="2087c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="2087c-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="2087c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2087c-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="2087c-110">Attributes</span></span>  
  
|<span data-ttu-id="2087c-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="2087c-111">Attribute</span></span>|<span data-ttu-id="2087c-112">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="2087c-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2087c-113">id</span><span class="sxs-lookup"><span data-stu-id="2087c-113">id</span></span>|<span data-ttu-id="2087c-114">Un atributo necesario que contiene una cadena que especifica un identificador único para un tipo con persistencia.</span><span class="sxs-lookup"><span data-stu-id="2087c-114">A required attribute that contains a string that specifies a unique identifier for a persistable type.</span></span>|  
|<span data-ttu-id="2087c-115">Nombre</span><span class="sxs-lookup"><span data-stu-id="2087c-115">name</span></span>|<span data-ttu-id="2087c-116">Un atributo opcional que contiene una cadena que especifica el nombre del tipo con persistencia.</span><span class="sxs-lookup"><span data-stu-id="2087c-116">An optional attribute that contains a string that specifies the name of the persistable type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2087c-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="2087c-117">Child Elements</span></span>  
 <span data-ttu-id="2087c-118">None</span><span class="sxs-lookup"><span data-stu-id="2087c-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2087c-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="2087c-119">Parent Elements</span></span>  
  
|<span data-ttu-id="2087c-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="2087c-120">Element</span></span>|<span data-ttu-id="2087c-121">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="2087c-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2087c-122">\<persistableTypes></span><span class="sxs-lookup"><span data-stu-id="2087c-122">\<persistableTypes></span></span>](persistabletypes.md)|<span data-ttu-id="2087c-123">Una colección de elementos de `persistableType`.</span><span class="sxs-lookup"><span data-stu-id="2087c-123">A collection of `persistableType` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2087c-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="2087c-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComPersistableTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ComPersistableTypeElement>
- [<span data-ttu-id="2087c-125">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="2087c-125">\<comContracts></span></span>](comcontracts.md)
- [<span data-ttu-id="2087c-126">Integración en aplicaciones COM+</span><span class="sxs-lookup"><span data-stu-id="2087c-126">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="2087c-127">Procedimientos: Configurar el servicio COM+</span><span class="sxs-lookup"><span data-stu-id="2087c-127">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
