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
ms.openlocfilehash: eed2a4d06906d2928be62aed20a75484c3eea946
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699765"
---
# <a name="oidentry-element"></a><span data-ttu-id="7963d-102">\<oidEntry >, elemento</span><span class="sxs-lookup"><span data-stu-id="7963d-102">\<oidEntry> Element</span></span>
<span data-ttu-id="7963d-103">Asigna un identificador de objeto (OID) ASN.1 a un nombre descriptivo.</span><span class="sxs-lookup"><span data-stu-id="7963d-103">Maps an ASN.1 object identifier (OID) to a friendly name.</span></span>  
  
[<span data-ttu-id="7963d-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="7963d-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="7963d-105">&nbsp; @ no__t-1[ **\<mscorlib >** ](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="7963d-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>  
<span data-ttu-id="7963d-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<cryptographySettings >** ](cryptographysettings-element.md)</span><span class="sxs-lookup"><span data-stu-id="7963d-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)</span></span>  
<span data-ttu-id="7963d-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5[ **\<oidMap >** ](oidmap-element.md)</span><span class="sxs-lookup"><span data-stu-id="7963d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oidMap>**](oidmap-element.md)</span></span>  
<span data-ttu-id="7963d-108">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 **\<oidEntry >**</span><span class="sxs-lookup"><span data-stu-id="7963d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<oidEntry>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7963d-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7963d-109">Syntax</span></span>  
  
```xml  
<oidEntry OID="object identifier number" name="friendly name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7963d-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="7963d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7963d-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="7963d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7963d-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="7963d-112">Attributes</span></span>  
  
|<span data-ttu-id="7963d-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="7963d-113">Attribute</span></span>|<span data-ttu-id="7963d-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="7963d-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7963d-115">**OID**</span><span class="sxs-lookup"><span data-stu-id="7963d-115">**OID**</span></span>|<span data-ttu-id="7963d-116">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="7963d-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="7963d-117">Especifica el OID ASN. 1 correspondiente al algoritmo implementado por la clase.</span><span class="sxs-lookup"><span data-stu-id="7963d-117">Specifies the ASN.1 OID corresponding to the algorithm implemented by your class.</span></span>|  
|<span data-ttu-id="7963d-118">**name**</span><span class="sxs-lookup"><span data-stu-id="7963d-118">**name**</span></span>|<span data-ttu-id="7963d-119">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="7963d-119">Required attribute.</span></span><br /><br /> <span data-ttu-id="7963d-120">Especifica el valor para el atributo de **nombre** en la etiqueta de [> \<nameEntry](nameentry-element.md) .</span><span class="sxs-lookup"><span data-stu-id="7963d-120">Specifies the value for the **name** attribute in the [\<nameEntry>](nameentry-element.md) tag.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7963d-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="7963d-121">Child Elements</span></span>  
 <span data-ttu-id="7963d-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="7963d-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7963d-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="7963d-123">Parent Elements</span></span>  
  
|<span data-ttu-id="7963d-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="7963d-124">Element</span></span>|<span data-ttu-id="7963d-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="7963d-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="7963d-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7963d-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="7963d-127">Contiene la configuración de criptografía.</span><span class="sxs-lookup"><span data-stu-id="7963d-127">Contains cryptography settings.</span></span>|  
|`mscorlib`|<span data-ttu-id="7963d-128">Contiene el `cryptographySettings` elemento.</span><span class="sxs-lookup"><span data-stu-id="7963d-128">Contains the `cryptographySettings` element.</span></span>|  
|`oidMap`|<span data-ttu-id="7963d-129">Contiene las asignaciones de identificador de objetos (OID) ASN. 1 a las clases.</span><span class="sxs-lookup"><span data-stu-id="7963d-129">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7963d-130">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7963d-130">Remarks</span></span>  
 <span data-ttu-id="7963d-131">Los identificadores de objeto ASN. 1 identifican los algoritmos en algunos formatos criptográficos.</span><span class="sxs-lookup"><span data-stu-id="7963d-131">ASN.1 object identifiers identify algorithms in some cryptographic formats.</span></span> <span data-ttu-id="7963d-132">Asigne identificadores de objeto a nombres descriptivos para los algoritmos que desee identificar.</span><span class="sxs-lookup"><span data-stu-id="7963d-132">Map object identifiers to friendly names for the algorithms you want to identify.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7963d-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7963d-133">Example</span></span>  
 <span data-ttu-id="7963d-134">En el ejemplo siguiente se muestra cómo usar el elemento **> \<oidEntry** para asignar un identificador de objeto para el algoritmo hash RIPEMD-160 a una implementación de ese algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="7963d-134">The following example shows how to use the **\<oidEntry>** element to map an object identifier for the RIPEMD-160 hash algorithm to an implementation of that hash algorithm.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7963d-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="7963d-135">See also</span></span>

- [<span data-ttu-id="7963d-136">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="7963d-136">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="7963d-137">Esquema de la configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="7963d-137">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="7963d-138">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="7963d-138">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="7963d-139">Configurar clases de criptografía</span><span class="sxs-lookup"><span data-stu-id="7963d-139">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
- [<span data-ttu-id="7963d-140">Asignar identificadores de objeto a algoritmos de criptografía</span><span class="sxs-lookup"><span data-stu-id="7963d-140">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../map-object-identifiers-to-cryptography-algorithms.md)
