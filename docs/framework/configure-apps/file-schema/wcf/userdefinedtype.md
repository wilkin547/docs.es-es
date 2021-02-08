---
description: 'Más información acerca de: <userDefinedType>'
title: <userDefinedType>
ms.date: 03/30/2017
ms.assetid: 0f70ec06-8249-4f0c-9f49-b4df59985fb8
ms.openlocfilehash: 11f4380f54abbdb0faf37998b07473e38ec9245f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99773425"
---
# \<userDefinedType>

<span data-ttu-id="ac393-102">Representa un tipo definido por el usuario (UDT) que se va a incluir en el contrato del servicio.</span><span class="sxs-lookup"><span data-stu-id="ac393-102">Represents a User Defined Type (UDT) that is to be included in the service contract.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContracts>**](comcontracts.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContract>**](comcontract.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<userDefinedTypes>**](userdefinedtypes.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<userDefinedType>**  
  
## <a name="syntax"></a><span data-ttu-id="ac393-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ac393-103">Syntax</span></span>  
  
```xml  
<comContracts>
  <comContract>
    <userDefinedTypes>
      <userDefinedType name="String"
                       typeLibID="String"
                       typeLibVersion="String"
                       typeDefID="String">
      </userDefinedType>
    </userDefinedTypes>
  </comContract>
</comContracts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ac393-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ac393-104">Attributes and Elements</span></span>  

 <span data-ttu-id="ac393-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ac393-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ac393-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="ac393-106">Attributes</span></span>  
  
|<span data-ttu-id="ac393-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="ac393-107">Attribute</span></span>|<span data-ttu-id="ac393-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="ac393-108">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="ac393-109">Un atributo opcional que contiene una cadena que proporciona el nombre de tipo legible.</span><span class="sxs-lookup"><span data-stu-id="ac393-109">An optional attribute that contains a string that provides the readable type name.</span></span> <span data-ttu-id="ac393-110">El tiempo de ejecución no lo usa, pero ayuda a que un lector distinga los tipos.</span><span class="sxs-lookup"><span data-stu-id="ac393-110">This is not used by the runtime but helps a reader to distinguish the types.</span></span>|  
|`TypeDefID`|<span data-ttu-id="ac393-111">Una cadena GUID que identifica el tipo UDT concreto dentro de la biblioteca de tipos registrados.</span><span class="sxs-lookup"><span data-stu-id="ac393-111">A GUID string that identifies the specific UDT type within the registered type library.</span></span>|  
|`TypeLibID`|<span data-ttu-id="ac393-112">Una cadena GUID que identifica la biblioteca de tipos registrados que define el tipo.</span><span class="sxs-lookup"><span data-stu-id="ac393-112">A GUID string that identifies the registered type library that defines the type.</span></span>|  
|`TypeLibVersion`|<span data-ttu-id="ac393-113">Una cadena que identifica la versión de biblioteca de tipos que define el tipo.</span><span class="sxs-lookup"><span data-stu-id="ac393-113">A string that identifies the type library version that defines the type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ac393-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ac393-114">Child Elements</span></span>  

 <span data-ttu-id="ac393-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="ac393-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ac393-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ac393-116">Parent Elements</span></span>  
  
|<span data-ttu-id="ac393-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="ac393-117">Element</span></span>|<span data-ttu-id="ac393-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="ac393-118">Description</span></span>|  
|-------------|-----------------|  
|`userDefinedTypes`|<span data-ttu-id="ac393-119">Una colección de elementos de `userDefinedType`.</span><span class="sxs-lookup"><span data-stu-id="ac393-119">A collection of `userDefinedType` elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ac393-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ac393-120">Remarks</span></span>  

 <span data-ttu-id="ac393-121">El tiempo de ejecución de integración de COM+ crea los servicios mediante la inspección de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="ac393-121">The COM+ integration runtime creates services by inspecting the type library.</span></span> <span data-ttu-id="ac393-122">Cuando un componente de COM+ contiene métodos que pasan una VARIANTE, el sistema no puede determinar los tipos reales que se van a pasar antes del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ac393-122">When a COM+ component contains methods that pass a VARIANT, the system cannot determine the actual types to be passed prior to runtime.</span></span> <span data-ttu-id="ac393-123">Por consiguiente, al intentar pasar un tipo definido por el usuario dentro de una VARIANTE , se produce un error porque no es un tipo conocido para la serialización.</span><span class="sxs-lookup"><span data-stu-id="ac393-123">Therefore, when you attempt to pass a User Defined Type (UDT) within a VARIANT, it fails because it is not a known type for serialization.</span></span>  
  
 <span data-ttu-id="ac393-124">Para prevenir este problema, puede agregar los UDT al archivo de configuración para que puedan estar incluidos como tipos conocidos en el contrato del servicio adecuado.</span><span class="sxs-lookup"><span data-stu-id="ac393-124">To circumvent this problem, you can add the UDTs to the configuration file so that they can be included as known types on the appropriate service contract.</span></span> <span data-ttu-id="ac393-125">Para ello, tiene que identificar de manera unívoca el UDT y los contratos, es decir, las interfaces COM originales que lo utilizan.</span><span class="sxs-lookup"><span data-stu-id="ac393-125">In order to do so, you have to uniquely identify the UDT and the contract(s), that is, the original COM interface(s) that uses it.</span></span>  
  
 <span data-ttu-id="ac393-126">El ejemplo siguiente muestra la adición de dos UDT concretos a la sección <`userDefinedTypes`> del archivo de configuración para este propósito.</span><span class="sxs-lookup"><span data-stu-id="ac393-126">The following example demonstrates adding two specific UDTs to the <`userDefinedTypes`> section of the configuration file for this purpose.</span></span>  
  
```xml  
<comContracts>
  <comContract contract="{5163B1E7-F0CF-4B6A-9A02-4AB654F34284}"
               namespace="http://tempuri.org/5163B1E7-F0CF-4B6A-9A02-4AB654F34284"
               name="_Broker"
               requireSession="true">
    <userDefinedTypes>
      <userDefinedType name="CustomerType"
                       typeLibID="{91DC728C-4F1A-45de-A9B6-B538E209CEA6}"
                       typeLibVersion="1.0"
                       typeDefID="{D129765C-F211-434e-825A-9A63198C41F2}">
      </userDefinedType>
      <userDefinedType name="AddressType"
                       typeLibID="{91DC728C-4F1A-45de-A9B6-B538E209CEA6}"
                       typeLibVersion="1.0"
                       typeDefID="{4616AE0D-687A-43B7-BC63-141AE3DFD099}">
      </userDefinedType>
    </userDefinedTypes>
    <exposedMethods>
      <exposedMethod name="BuyStock" />
      <exposedMethod name="SellStock" />
      <exposedMethod name="ExecuteTransaction" />
    </exposedMethods>
  </comContract>
</comContracts>
```  
  
 <span data-ttu-id="ac393-127">Cuando se inicializa el servicio, el tiempo de ejecución de integración busca los tipos especificados y los agrega a la colección de tipos conocidos para los contratos especificados.</span><span class="sxs-lookup"><span data-stu-id="ac393-127">When the service is initialized, the integration runtime looks up the specified types and adds them to the known types collection for the specified contracts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac393-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="ac393-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComContractElement.UserDefinedTypes%2A>
- <xref:System.ServiceModel.Configuration.ComUdtElementCollection>
- <xref:System.ServiceModel.Configuration.ComUdtElement>
- [\<comContracts>](comcontracts.md)
- [<span data-ttu-id="ac393-129">Integración con aplicaciones COM+</span><span class="sxs-lookup"><span data-stu-id="ac393-129">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="ac393-130">Procedimiento para configurar los parámetros de los servicios COM+</span><span class="sxs-lookup"><span data-stu-id="ac393-130">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
