---
description: 'Más información acerca de: <persistableType>'
title: <persistableType>
ms.date: 03/30/2017
ms.assetid: e5425fe6-523a-4076-aab4-2c2515b1d830
ms.openlocfilehash: eadbb951d751dd88ce974edc8d5b343a1469b758
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99683637"
---
# \<persistableType>

<span data-ttu-id="ba4ed-102">Especifica todos los tipos con persistencia.</span><span class="sxs-lookup"><span data-stu-id="ba4ed-102">Specifies all the persistable types.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContracts>**](comcontracts.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContract>**](comcontract.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<persistableTypes>**](persistabletypes.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<persistableType>**  
  
## <a name="syntax"></a><span data-ttu-id="ba4ed-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ba4ed-103">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="ba4ed-104">Tipo</span><span class="sxs-lookup"><span data-stu-id="ba4ed-104">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ba4ed-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ba4ed-105">Attributes and Elements</span></span>  

 <span data-ttu-id="ba4ed-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ba4ed-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ba4ed-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="ba4ed-107">Attributes</span></span>  
  
|<span data-ttu-id="ba4ed-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="ba4ed-108">Attribute</span></span>|<span data-ttu-id="ba4ed-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="ba4ed-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ba4ed-110">id</span><span class="sxs-lookup"><span data-stu-id="ba4ed-110">id</span></span>|<span data-ttu-id="ba4ed-111">Un atributo necesario que contiene una cadena que especifica un identificador único para un tipo con persistencia.</span><span class="sxs-lookup"><span data-stu-id="ba4ed-111">A required attribute that contains a string that specifies a unique identifier for a persistable type.</span></span>|  
|<span data-ttu-id="ba4ed-112">name</span><span class="sxs-lookup"><span data-stu-id="ba4ed-112">name</span></span>|<span data-ttu-id="ba4ed-113">Un atributo opcional que contiene una cadena que especifica el nombre del tipo con persistencia.</span><span class="sxs-lookup"><span data-stu-id="ba4ed-113">An optional attribute that contains a string that specifies the name of the persistable type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ba4ed-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ba4ed-114">Child Elements</span></span>  

 <span data-ttu-id="ba4ed-115">None</span><span class="sxs-lookup"><span data-stu-id="ba4ed-115">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ba4ed-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ba4ed-116">Parent Elements</span></span>  
  
|<span data-ttu-id="ba4ed-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="ba4ed-117">Element</span></span>|<span data-ttu-id="ba4ed-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="ba4ed-118">Description</span></span>|  
|-------------|-----------------|  
|[\<persistableTypes>](persistabletypes.md)|<span data-ttu-id="ba4ed-119">Una colección de elementos de `persistableType`.</span><span class="sxs-lookup"><span data-stu-id="ba4ed-119">A collection of `persistableType` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ba4ed-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="ba4ed-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComPersistableTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ComPersistableTypeElement>
- [\<comContracts>](comcontracts.md)
- [<span data-ttu-id="ba4ed-121">Integración con aplicaciones COM+</span><span class="sxs-lookup"><span data-stu-id="ba4ed-121">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="ba4ed-122">Procedimiento para configurar los parámetros de los servicios COM+</span><span class="sxs-lookup"><span data-stu-id="ba4ed-122">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
