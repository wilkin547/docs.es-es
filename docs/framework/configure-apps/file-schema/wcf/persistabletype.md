---
title: <persistableType>
ms.date: 03/30/2017
ms.assetid: e5425fe6-523a-4076-aab4-2c2515b1d830
ms.openlocfilehash: 3ea99d360ceb1e3fe6e97cbf9c8827dd7c853f63
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55256529"
---
# <a name="persistabletype"></a><span data-ttu-id="fce21-101">\<persistableType></span><span class="sxs-lookup"><span data-stu-id="fce21-101">\<persistableType></span></span>
<span data-ttu-id="fce21-102">Especifica todos los tipos con persistencia.</span><span class="sxs-lookup"><span data-stu-id="fce21-102">Specifies all the persistable types.</span></span>  
  
 <span data-ttu-id="fce21-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="fce21-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="fce21-104">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="fce21-104">\<comContracts></span></span>  
<span data-ttu-id="fce21-105">\<comContract></span><span class="sxs-lookup"><span data-stu-id="fce21-105">\<comContract></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fce21-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fce21-106">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="fce21-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="fce21-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fce21-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="fce21-108">Attributes and Elements</span></span>  
 <span data-ttu-id="fce21-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="fce21-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fce21-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="fce21-110">Attributes</span></span>  
  
|<span data-ttu-id="fce21-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="fce21-111">Attribute</span></span>|<span data-ttu-id="fce21-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="fce21-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fce21-113">id</span><span class="sxs-lookup"><span data-stu-id="fce21-113">id</span></span>|<span data-ttu-id="fce21-114">Un atributo necesario que contiene una cadena que especifica un identificador único para un tipo con persistencia.</span><span class="sxs-lookup"><span data-stu-id="fce21-114">A required attribute that contains a string that specifies a unique identifier for a persistable type.</span></span>|  
|<span data-ttu-id="fce21-115">name</span><span class="sxs-lookup"><span data-stu-id="fce21-115">name</span></span>|<span data-ttu-id="fce21-116">Un atributo opcional que contiene una cadena que especifica el nombre del tipo con persistencia.</span><span class="sxs-lookup"><span data-stu-id="fce21-116">An optional attribute that contains a string that specifies the name of the persistable type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fce21-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="fce21-117">Child Elements</span></span>  
 <span data-ttu-id="fce21-118">Ninguna</span><span class="sxs-lookup"><span data-stu-id="fce21-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fce21-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="fce21-119">Parent Elements</span></span>  
  
|<span data-ttu-id="fce21-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="fce21-120">Element</span></span>|<span data-ttu-id="fce21-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="fce21-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fce21-122">\<persistableTypes></span><span class="sxs-lookup"><span data-stu-id="fce21-122">\<persistableTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md)|<span data-ttu-id="fce21-123">Una colección de elementos de `persistableType`.</span><span class="sxs-lookup"><span data-stu-id="fce21-123">A collection of `persistableType` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fce21-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="fce21-124">See also</span></span>
- <xref:System.ServiceModel.Configuration.ComPersistableTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ComPersistableTypeElement>
- [<span data-ttu-id="fce21-125">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="fce21-125">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)
- [<span data-ttu-id="fce21-126">Integración en aplicaciones COM+</span><span class="sxs-lookup"><span data-stu-id="fce21-126">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="fce21-127">Cómo: Configurar el servicio COM +</span><span class="sxs-lookup"><span data-stu-id="fce21-127">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
