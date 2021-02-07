---
description: 'Más información acerca de: <oidEntry> elemento'
title: <oidEntry> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/oidMap/oidEntry
- http://schemas.microsoft.com/.NetConfiguration/v2.0#oidEntry
helpviewer_keywords:
- <oidEntry> element
- oidEntry element
ms.assetid: 22fb88b0-bf27-489c-9ca0-e65950ac136c
ms.openlocfilehash: d5fe22018377e247ffa0b6addb58cbeee7119e66
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99698757"
---
# <a name="oidentry-element"></a><span data-ttu-id="e6265-103">\<oidEntry> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="e6265-103">\<oidEntry> Element</span></span>

<span data-ttu-id="e6265-104">Asigna un identificador de objeto (OID) ASN.1 a un nombre descriptivo.</span><span class="sxs-lookup"><span data-stu-id="e6265-104">Maps an ASN.1 object identifier (OID) to a friendly name.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oidMap>**](oidmap-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<oidEntry>**

## <a name="syntax"></a><span data-ttu-id="e6265-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e6265-105">Syntax</span></span>  
  
```xml  
<oidEntry OID="object identifier number" name="friendly name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e6265-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e6265-106">Attributes and Elements</span></span>  

 <span data-ttu-id="e6265-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e6265-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e6265-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="e6265-108">Attributes</span></span>  
  
|<span data-ttu-id="e6265-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="e6265-109">Attribute</span></span>|<span data-ttu-id="e6265-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="e6265-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e6265-111">**OID**</span><span class="sxs-lookup"><span data-stu-id="e6265-111">**OID**</span></span>|<span data-ttu-id="e6265-112">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="e6265-112">Required attribute.</span></span><br /><br /> <span data-ttu-id="e6265-113">Especifica el OID ASN. 1 correspondiente al algoritmo implementado por la clase.</span><span class="sxs-lookup"><span data-stu-id="e6265-113">Specifies the ASN.1 OID corresponding to the algorithm implemented by your class.</span></span>|  
|<span data-ttu-id="e6265-114">**name**</span><span class="sxs-lookup"><span data-stu-id="e6265-114">**name**</span></span>|<span data-ttu-id="e6265-115">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="e6265-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="e6265-116">Especifica el valor para el atributo de **nombre** en la [\<nameEntry>](nameentry-element.md) etiqueta.</span><span class="sxs-lookup"><span data-stu-id="e6265-116">Specifies the value for the **name** attribute in the [\<nameEntry>](nameentry-element.md) tag.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e6265-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e6265-117">Child Elements</span></span>  

 <span data-ttu-id="e6265-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e6265-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e6265-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e6265-119">Parent Elements</span></span>  
  
|<span data-ttu-id="e6265-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="e6265-120">Element</span></span>|<span data-ttu-id="e6265-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="e6265-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e6265-122">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e6265-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="e6265-123">Contiene la configuración de criptografía.</span><span class="sxs-lookup"><span data-stu-id="e6265-123">Contains cryptography settings.</span></span>|  
|`mscorlib`|<span data-ttu-id="e6265-124">Contiene el `cryptographySettings` elemento.</span><span class="sxs-lookup"><span data-stu-id="e6265-124">Contains the `cryptographySettings` element.</span></span>|  
|`oidMap`|<span data-ttu-id="e6265-125">Contiene las asignaciones de identificador de objetos (OID) ASN. 1 a las clases.</span><span class="sxs-lookup"><span data-stu-id="e6265-125">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e6265-126">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e6265-126">Remarks</span></span>  

 <span data-ttu-id="e6265-127">Los identificadores de objeto ASN. 1 identifican los algoritmos en algunos formatos criptográficos.</span><span class="sxs-lookup"><span data-stu-id="e6265-127">ASN.1 object identifiers identify algorithms in some cryptographic formats.</span></span> <span data-ttu-id="e6265-128">Asigne identificadores de objeto a nombres descriptivos para los algoritmos que desee identificar.</span><span class="sxs-lookup"><span data-stu-id="e6265-128">Map object identifiers to friendly names for the algorithms you want to identify.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6265-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e6265-129">Example</span></span>  

 <span data-ttu-id="e6265-130">En el ejemplo siguiente se muestra cómo usar el **\<oidEntry>** elemento para asignar un identificador de objeto para el algoritmo hash RIPEMD-160 a una implementación de ese algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="e6265-130">The following example shows how to use the **\<oidEntry>** element to map an object identifier for the RIPEMD-160 hash algorithm to an implementation of that hash algorithm.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCrypto="MyCryptoClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="RIPEMD-160" class="MyCrypto"/>  
         </cryptoNameMapping>  
         <oidMap>  
            <oidEntry OID="1.3.36.3.2.1"   name="MyCryptoClass"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e6265-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="e6265-131">See also</span></span>

- [<span data-ttu-id="e6265-132">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="e6265-132">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="e6265-133">Esquema de configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="e6265-133">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="e6265-134">servicios criptográficos</span><span class="sxs-lookup"><span data-stu-id="e6265-134">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="e6265-135">Configurar clases de criptografía</span><span class="sxs-lookup"><span data-stu-id="e6265-135">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
- [<span data-ttu-id="e6265-136">Asignar identificadores de objeto a algoritmos de criptografía</span><span class="sxs-lookup"><span data-stu-id="e6265-136">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../map-object-identifiers-to-cryptography-algorithms.md)
