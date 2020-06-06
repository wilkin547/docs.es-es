---
title: <oidEntry> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/oidMap/oidEntry
- http://schemas.microsoft.com/.NetConfiguration/v2.0#oidEntry
helpviewer_keywords:
- <oidEntry> element
- oidEntry element
ms.assetid: 22fb88b0-bf27-489c-9ca0-e65950ac136c
ms.openlocfilehash: 4564cf59e3b6cfbdcd9dca06cd0f966d524834de
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "74088548"
---
# <a name="oidentry-element"></a><span data-ttu-id="bdef1-102">\<oidEntry> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="bdef1-102">\<oidEntry> Element</span></span>
<span data-ttu-id="bdef1-103">Asigna un identificador de objeto (OID) ASN.1 a un nombre descriptivo.</span><span class="sxs-lookup"><span data-stu-id="bdef1-103">Maps an ASN.1 object identifier (OID) to a friendly name.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oidMap>**](oidmap-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<oidEntry>**

## <a name="syntax"></a><span data-ttu-id="bdef1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bdef1-104">Syntax</span></span>  
  
```xml  
<oidEntry OID="object identifier number" name="friendly name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bdef1-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="bdef1-105">Attributes and Elements</span></span>  
 <span data-ttu-id="bdef1-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="bdef1-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bdef1-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="bdef1-107">Attributes</span></span>  
  
|<span data-ttu-id="bdef1-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="bdef1-108">Attribute</span></span>|<span data-ttu-id="bdef1-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="bdef1-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bdef1-110">**OID**</span><span class="sxs-lookup"><span data-stu-id="bdef1-110">**OID**</span></span>|<span data-ttu-id="bdef1-111">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="bdef1-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="bdef1-112">Especifica el OID ASN. 1 correspondiente al algoritmo implementado por la clase.</span><span class="sxs-lookup"><span data-stu-id="bdef1-112">Specifies the ASN.1 OID corresponding to the algorithm implemented by your class.</span></span>|  
|<span data-ttu-id="bdef1-113">**name**</span><span class="sxs-lookup"><span data-stu-id="bdef1-113">**name**</span></span>|<span data-ttu-id="bdef1-114">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="bdef1-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="bdef1-115">Especifica el valor para el atributo de **nombre** en la [\<nameEntry>](nameentry-element.md) etiqueta.</span><span class="sxs-lookup"><span data-stu-id="bdef1-115">Specifies the value for the **name** attribute in the [\<nameEntry>](nameentry-element.md) tag.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bdef1-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="bdef1-116">Child Elements</span></span>  
 <span data-ttu-id="bdef1-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="bdef1-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bdef1-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="bdef1-118">Parent Elements</span></span>  
  
|<span data-ttu-id="bdef1-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="bdef1-119">Element</span></span>|<span data-ttu-id="bdef1-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="bdef1-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="bdef1-121">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bdef1-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="bdef1-122">Contiene la configuración de criptografía.</span><span class="sxs-lookup"><span data-stu-id="bdef1-122">Contains cryptography settings.</span></span>|  
|`mscorlib`|<span data-ttu-id="bdef1-123">Contiene el `cryptographySettings` elemento.</span><span class="sxs-lookup"><span data-stu-id="bdef1-123">Contains the `cryptographySettings` element.</span></span>|  
|`oidMap`|<span data-ttu-id="bdef1-124">Contiene las asignaciones de identificador de objetos (OID) ASN. 1 a las clases.</span><span class="sxs-lookup"><span data-stu-id="bdef1-124">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bdef1-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bdef1-125">Remarks</span></span>  
 <span data-ttu-id="bdef1-126">Los identificadores de objeto ASN. 1 identifican los algoritmos en algunos formatos criptográficos.</span><span class="sxs-lookup"><span data-stu-id="bdef1-126">ASN.1 object identifiers identify algorithms in some cryptographic formats.</span></span> <span data-ttu-id="bdef1-127">Asigne identificadores de objeto a nombres descriptivos para los algoritmos que desee identificar.</span><span class="sxs-lookup"><span data-stu-id="bdef1-127">Map object identifiers to friendly names for the algorithms you want to identify.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bdef1-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bdef1-128">Example</span></span>  
 <span data-ttu-id="bdef1-129">En el ejemplo siguiente se muestra cómo usar el **\<oidEntry>** elemento para asignar un identificador de objeto para el algoritmo hash RIPEMD-160 a una implementación de ese algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="bdef1-129">The following example shows how to use the **\<oidEntry>** element to map an object identifier for the RIPEMD-160 hash algorithm to an implementation of that hash algorithm.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bdef1-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="bdef1-130">See also</span></span>

- [<span data-ttu-id="bdef1-131">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="bdef1-131">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="bdef1-132">Esquema de la configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="bdef1-132">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="bdef1-133">Servicios criptográficos</span><span class="sxs-lookup"><span data-stu-id="bdef1-133">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="bdef1-134">Configurar clases de criptografía</span><span class="sxs-lookup"><span data-stu-id="bdef1-134">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
- [<span data-ttu-id="bdef1-135">Asignar identificadores de objeto a algoritmos de criptografía</span><span class="sxs-lookup"><span data-stu-id="bdef1-135">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../map-object-identifiers-to-cryptography-algorithms.md)
