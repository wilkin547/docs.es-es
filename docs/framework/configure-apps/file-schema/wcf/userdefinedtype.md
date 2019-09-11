---
title: <userDefinedType>
ms.date: 03/30/2017
ms.assetid: 0f70ec06-8249-4f0c-9f49-b4df59985fb8
ms.openlocfilehash: 7a76e5a90fe3218bc0302501b71daa9de0b098bc
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854836"
---
# <a name="userdefinedtype"></a><span data-ttu-id="e6db1-101">\<userDefinedType></span><span class="sxs-lookup"><span data-stu-id="e6db1-101">\<userDefinedType></span></span>
<span data-ttu-id="e6db1-102">Representa un tipo definido por el usuario (UDT) que se va a incluir en el contrato del servicio.</span><span class="sxs-lookup"><span data-stu-id="e6db1-102">Represents a User Defined Type (UDT) that is to be included in the service contract.</span></span>  
  
<span data-ttu-id="e6db1-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e6db1-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e6db1-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="e6db1-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="e6db1-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de compactos**](comcontracts.md)</span><span class="sxs-lookup"><span data-stu-id="e6db1-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContracts>**](comcontracts.md)</span></span>\
<span data-ttu-id="e6db1-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> compactos**](comcontract.md)</span><span class="sxs-lookup"><span data-stu-id="e6db1-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContract>**](comcontract.md)</span></span>\
<span data-ttu-id="e6db1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> userDefinedTypes**](userdefinedtypes.md)</span><span class="sxs-lookup"><span data-stu-id="e6db1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<userDefinedTypes>**](userdefinedtypes.md)</span></span>\
<span data-ttu-id="e6db1-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> userDefinedType**</span><span class="sxs-lookup"><span data-stu-id="e6db1-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<userDefinedType>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6db1-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e6db1-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e6db1-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e6db1-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e6db1-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e6db1-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e6db1-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="e6db1-112">Attributes</span></span>  
  
|<span data-ttu-id="e6db1-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="e6db1-113">Attribute</span></span>|<span data-ttu-id="e6db1-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="e6db1-114">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="e6db1-115">Un atributo opcional que contiene una cadena que proporciona el nombre de tipo legible.</span><span class="sxs-lookup"><span data-stu-id="e6db1-115">An optional attribute that contains a string that provides the readable type name.</span></span> <span data-ttu-id="e6db1-116">El tiempo de ejecución no lo usa, pero ayuda a que un lector distinga los tipos.</span><span class="sxs-lookup"><span data-stu-id="e6db1-116">This is not used by the runtime but helps a reader to distinguish the types.</span></span>|  
|`TypeDefID`|<span data-ttu-id="e6db1-117">Una cadena GUID que identifica el tipo UDT concreto dentro de la biblioteca de tipos registrados.</span><span class="sxs-lookup"><span data-stu-id="e6db1-117">A GUID string that identifies the specific UDT type within the registered type library.</span></span>|  
|`TypeLibID`|<span data-ttu-id="e6db1-118">Una cadena GUID que identifica la biblioteca de tipos registrados que define el tipo.</span><span class="sxs-lookup"><span data-stu-id="e6db1-118">A GUID string that identifies the registered type library that defines the type.</span></span>|  
|`TypeLibVersion`|<span data-ttu-id="e6db1-119">Una cadena que identifica la versión de biblioteca de tipos que define el tipo.</span><span class="sxs-lookup"><span data-stu-id="e6db1-119">A string that identifies the type library version that defines the type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e6db1-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e6db1-120">Child Elements</span></span>  
 <span data-ttu-id="e6db1-121">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e6db1-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e6db1-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e6db1-122">Parent Elements</span></span>  
  
|<span data-ttu-id="e6db1-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="e6db1-123">Element</span></span>|<span data-ttu-id="e6db1-124">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="e6db1-124">Description</span></span>|  
|-------------|-----------------|  
|`userDefinedTypes`|<span data-ttu-id="e6db1-125">Una colección de elementos de `userDefinedType`.</span><span class="sxs-lookup"><span data-stu-id="e6db1-125">A collection of `userDefinedType` elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e6db1-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e6db1-126">Remarks</span></span>  
 <span data-ttu-id="e6db1-127">El tiempo de ejecución de integración de COM+ crea los servicios mediante la inspección de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="e6db1-127">The COM+ integration runtime creates services by inspecting the type library.</span></span> <span data-ttu-id="e6db1-128">Cuando un componente de COM+ contiene métodos que pasan una VARIANTE, el sistema no puede determinar los tipos reales que se van a pasar antes del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="e6db1-128">When a COM+ component contains methods that pass a VARIANT, the system cannot determine the actual types to be passed prior to runtime.</span></span> <span data-ttu-id="e6db1-129">Por consiguiente, al intentar pasar un tipo definido por el usuario dentro de una VARIANTE , se produce un error porque no es un tipo conocido para la serialización.</span><span class="sxs-lookup"><span data-stu-id="e6db1-129">Therefore, when you attempt to pass a User Defined Type (UDT) within a VARIANT, it fails because it is not a known type for serialization.</span></span>  
  
 <span data-ttu-id="e6db1-130">Para prevenir este problema, puede agregar los UDT al archivo de configuración para que puedan estar incluidos como tipos conocidos en el contrato del servicio adecuado.</span><span class="sxs-lookup"><span data-stu-id="e6db1-130">To circumvent this problem, you can add the UDTs to the configuration file so that they can be included as known types on the appropriate service contract.</span></span> <span data-ttu-id="e6db1-131">Para ello, tiene que identificar de manera unívoca el UDT y los contratos, es decir, las interfaces COM originales que lo utilizan.</span><span class="sxs-lookup"><span data-stu-id="e6db1-131">In order to do so, you have to uniquely identify the UDT and the contract(s), that is, the original COM interface(s) that uses it.</span></span>  
  
 <span data-ttu-id="e6db1-132">En el ejemplo siguiente se muestra cómo agregar dos UDT concretos`userDefinedTypes`a la sección < > del archivo de configuración para este propósito.</span><span class="sxs-lookup"><span data-stu-id="e6db1-132">The following example demonstrates adding two specific UDTs to the <`userDefinedTypes`> section of the configuration file for this purpose.</span></span>  
  
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
  
 <span data-ttu-id="e6db1-133">Cuando se inicializa el servicio, el tiempo de ejecución de integración busca los tipos especificados y los agrega a la colección de tipos conocidos para los contratos especificados.</span><span class="sxs-lookup"><span data-stu-id="e6db1-133">When the service is initialized, the integration runtime looks up the specified types and adds them to the known types collection for the specified contracts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6db1-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="e6db1-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComContractElement.UserDefinedTypes%2A>
- <xref:System.ServiceModel.Configuration.ComUdtElementCollection>
- <xref:System.ServiceModel.Configuration.ComUdtElement>
- [<span data-ttu-id="e6db1-135">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="e6db1-135">\<comContracts></span></span>](comcontracts.md)
- [<span data-ttu-id="e6db1-136">Integración en aplicaciones COM+</span><span class="sxs-lookup"><span data-stu-id="e6db1-136">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="e6db1-137">Cómo: Configurar el servicio COM+</span><span class="sxs-lookup"><span data-stu-id="e6db1-137">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
