---
title: <oidMap> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#oidMap
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/oidMap
helpviewer_keywords:
- <oidMap> element
- oidMap element
ms.assetid: 7f0c2246-c070-4748-b96a-2f66a296c539
ms.openlocfilehash: d2929167f5a7de96a868cd1ac884d2203d09dfb6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927527"
---
# <a name="oidmap-element"></a><span data-ttu-id="837bd-102">\<oidMap >, elemento</span><span class="sxs-lookup"><span data-stu-id="837bd-102">\<oidMap> Element</span></span>
<span data-ttu-id="837bd-103">Contiene las asignaciones de identificador de objetos (OID) ASN. 1 a las clases.</span><span class="sxs-lookup"><span data-stu-id="837bd-103">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>  
  
 <span data-ttu-id="837bd-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="837bd-104">\<configuration></span></span>  
<span data-ttu-id="837bd-105">\<mscorlib></span><span class="sxs-lookup"><span data-stu-id="837bd-105">\<mscorlib></span></span>  
<span data-ttu-id="837bd-106">\<cryptographySettings></span><span class="sxs-lookup"><span data-stu-id="837bd-106">\<cryptographySettings></span></span>  
<span data-ttu-id="837bd-107">\<oidMap></span><span class="sxs-lookup"><span data-stu-id="837bd-107">\<oidMap></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="837bd-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="837bd-108">Syntax</span></span>  
  
```xml  
<oidMap>   
</oidMap>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="837bd-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="837bd-109">Attributes and Elements</span></span>  
 <span data-ttu-id="837bd-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="837bd-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="837bd-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="837bd-111">Attributes</span></span>  
 <span data-ttu-id="837bd-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="837bd-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="837bd-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="837bd-113">Child Elements</span></span>  
  
|<span data-ttu-id="837bd-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="837bd-114">Element</span></span>|<span data-ttu-id="837bd-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="837bd-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="837bd-116">\<oidEntry></span><span class="sxs-lookup"><span data-stu-id="837bd-116">\<oidEntry></span></span>](oidentry-element.md)|<span data-ttu-id="837bd-117">Asigna un OID ASN. 1 a un nombre descriptivo.</span><span class="sxs-lookup"><span data-stu-id="837bd-117">Maps an ASN.1 OID to a friendly name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="837bd-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="837bd-118">Parent Elements</span></span>  
  
|<span data-ttu-id="837bd-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="837bd-119">Element</span></span>|<span data-ttu-id="837bd-120">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="837bd-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="837bd-121">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="837bd-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="837bd-122">Contiene la configuración de criptografía.</span><span class="sxs-lookup"><span data-stu-id="837bd-122">Contains cryptography settings.</span></span>|  
|`mscorlib`|<span data-ttu-id="837bd-123">Contiene el `cryptographySettings` elemento.</span><span class="sxs-lookup"><span data-stu-id="837bd-123">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="837bd-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="837bd-124">Example</span></span>  
 <span data-ttu-id="837bd-125">En el ejemplo siguiente se muestra cómo usar  **\<** el elemento > de oidMap para que contenga una asignación de un OID para el algoritmo hash RIPEMD-160 a una implementación de ese algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="837bd-125">The following example shows how to use the **\<oidMap>** element to contain a mapping of an OID for the RIPEMD-160 hash algorithm to an implementation of that hash algorithm.</span></span>  
  
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
            <oidEntry OID="1.3.36.3.2.1"  name="MyCryptoClass"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="837bd-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="837bd-126">See also</span></span>

- [<span data-ttu-id="837bd-127">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="837bd-127">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="837bd-128">Esquema de la configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="837bd-128">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="837bd-129">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="837bd-129">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="837bd-130">Configurar clases de criptografía</span><span class="sxs-lookup"><span data-stu-id="837bd-130">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
- [<span data-ttu-id="837bd-131">Asignar identificadores de objeto a algoritmos de criptografía</span><span class="sxs-lookup"><span data-stu-id="837bd-131">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../map-object-identifiers-to-cryptography-algorithms.md)
