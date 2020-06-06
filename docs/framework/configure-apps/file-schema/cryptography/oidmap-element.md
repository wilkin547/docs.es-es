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
ms.openlocfilehash: a28eaf68fe1e6ab3f26592eee5ae2d0f2e7a3256
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155172"
---
# <a name="oidmap-element"></a><span data-ttu-id="03d9f-102">\<oidMap> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="03d9f-102">\<oidMap> Element</span></span>
<span data-ttu-id="03d9f-103">Contiene las asignaciones de identificador de objetos (OID) ASN. 1 a las clases.</span><span class="sxs-lookup"><span data-stu-id="03d9f-103">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<oidMap>**

## <a name="syntax"></a><span data-ttu-id="03d9f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="03d9f-104">Syntax</span></span>  
  
```xml  
<oidMap>
</oidMap>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="03d9f-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="03d9f-105">Attributes and Elements</span></span>  
 <span data-ttu-id="03d9f-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="03d9f-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="03d9f-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="03d9f-107">Attributes</span></span>  
 <span data-ttu-id="03d9f-108">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="03d9f-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="03d9f-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="03d9f-109">Child Elements</span></span>  
  
|<span data-ttu-id="03d9f-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="03d9f-110">Element</span></span>|<span data-ttu-id="03d9f-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="03d9f-111">Description</span></span>|  
|-------------|-----------------|  
|[\<oidEntry>](oidentry-element.md)|<span data-ttu-id="03d9f-112">Asigna un OID ASN. 1 a un nombre descriptivo.</span><span class="sxs-lookup"><span data-stu-id="03d9f-112">Maps an ASN.1 OID to a friendly name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="03d9f-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="03d9f-113">Parent Elements</span></span>  
  
|<span data-ttu-id="03d9f-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="03d9f-114">Element</span></span>|<span data-ttu-id="03d9f-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="03d9f-115">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="03d9f-116">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="03d9f-116">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="03d9f-117">Contiene la configuración de criptografía.</span><span class="sxs-lookup"><span data-stu-id="03d9f-117">Contains cryptography settings.</span></span>|  
|`mscorlib`|<span data-ttu-id="03d9f-118">Contiene el `cryptographySettings` elemento.</span><span class="sxs-lookup"><span data-stu-id="03d9f-118">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="03d9f-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="03d9f-119">Example</span></span>  
 <span data-ttu-id="03d9f-120">En el ejemplo siguiente se muestra cómo usar el **\<oidMap>** elemento para que contenga una asignación de un OID para el algoritmo hash RIPEMD-160 a una implementación de ese algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="03d9f-120">The following example shows how to use the **\<oidMap>** element to contain a mapping of an OID for the RIPEMD-160 hash algorithm to an implementation of that hash algorithm.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="03d9f-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="03d9f-121">See also</span></span>

- [<span data-ttu-id="03d9f-122">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="03d9f-122">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="03d9f-123">Esquema de la configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="03d9f-123">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="03d9f-124">Servicios criptográficos</span><span class="sxs-lookup"><span data-stu-id="03d9f-124">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="03d9f-125">Configurar clases de criptografía</span><span class="sxs-lookup"><span data-stu-id="03d9f-125">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
- [<span data-ttu-id="03d9f-126">Asignar identificadores de objeto a algoritmos de criptografía</span><span class="sxs-lookup"><span data-stu-id="03d9f-126">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../map-object-identifiers-to-cryptography-algorithms.md)
