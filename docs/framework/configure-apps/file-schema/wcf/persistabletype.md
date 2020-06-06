---
title: <persistableType>
ms.date: 03/30/2017
ms.assetid: e5425fe6-523a-4076-aab4-2c2515b1d830
ms.openlocfilehash: 328caaefe0cc24da45b460cab0a672dc8a6ccce1
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855073"
---
# \<persistableType>
<span data-ttu-id="8457f-101">Especifica todos los tipos con persistencia.</span><span class="sxs-lookup"><span data-stu-id="8457f-101">Specifies all the persistable types.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContracts>**](comcontracts.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContract>**](comcontract.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<persistableTypes>**](persistabletypes.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<persistableType>**  
  
## <a name="syntax"></a><span data-ttu-id="8457f-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8457f-102">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="8457f-103">Tipo</span><span class="sxs-lookup"><span data-stu-id="8457f-103">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8457f-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="8457f-104">Attributes and Elements</span></span>  
 <span data-ttu-id="8457f-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="8457f-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8457f-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="8457f-106">Attributes</span></span>  
  
|<span data-ttu-id="8457f-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="8457f-107">Attribute</span></span>|<span data-ttu-id="8457f-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="8457f-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8457f-109">id</span><span class="sxs-lookup"><span data-stu-id="8457f-109">id</span></span>|<span data-ttu-id="8457f-110">Un atributo necesario que contiene una cadena que especifica un identificador único para un tipo con persistencia.</span><span class="sxs-lookup"><span data-stu-id="8457f-110">A required attribute that contains a string that specifies a unique identifier for a persistable type.</span></span>|  
|<span data-ttu-id="8457f-111">name</span><span class="sxs-lookup"><span data-stu-id="8457f-111">name</span></span>|<span data-ttu-id="8457f-112">Un atributo opcional que contiene una cadena que especifica el nombre del tipo con persistencia.</span><span class="sxs-lookup"><span data-stu-id="8457f-112">An optional attribute that contains a string that specifies the name of the persistable type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8457f-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8457f-113">Child Elements</span></span>  
 <span data-ttu-id="8457f-114">None</span><span class="sxs-lookup"><span data-stu-id="8457f-114">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8457f-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8457f-115">Parent Elements</span></span>  
  
|<span data-ttu-id="8457f-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="8457f-116">Element</span></span>|<span data-ttu-id="8457f-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="8457f-117">Description</span></span>|  
|-------------|-----------------|  
|[\<persistableTypes>](persistabletypes.md)|<span data-ttu-id="8457f-118">Una colección de elementos de `persistableType`.</span><span class="sxs-lookup"><span data-stu-id="8457f-118">A collection of `persistableType` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8457f-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8457f-119">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComPersistableTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ComPersistableTypeElement>
- [\<comContracts>](comcontracts.md)
- [<span data-ttu-id="8457f-120">Integración con aplicaciones COM+</span><span class="sxs-lookup"><span data-stu-id="8457f-120">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="8457f-121">Procedimiento para configurar los parámetros de los servicios COM+</span><span class="sxs-lookup"><span data-stu-id="8457f-121">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
