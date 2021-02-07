---
description: 'Más información acerca de: <oidMap> elemento'
title: <oidMap> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#oidMap
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/oidMap
helpviewer_keywords:
- <oidMap> element
- oidMap element
ms.assetid: 7f0c2246-c070-4748-b96a-2f66a296c539
ms.openlocfilehash: 9a71cc54546f49fcada90a0f9915d44d1fc65e89
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99729997"
---
# <a name="oidmap-element"></a><span data-ttu-id="7a780-103">\<oidMap> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="7a780-103">\<oidMap> Element</span></span>

<span data-ttu-id="7a780-104">Contiene las asignaciones de identificador de objetos (OID) ASN. 1 a las clases.</span><span class="sxs-lookup"><span data-stu-id="7a780-104">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<oidMap>**

## <a name="syntax"></a><span data-ttu-id="7a780-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7a780-105">Syntax</span></span>  
  
```xml  
<oidMap>
</oidMap>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7a780-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="7a780-106">Attributes and Elements</span></span>  

 <span data-ttu-id="7a780-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="7a780-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7a780-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="7a780-108">Attributes</span></span>  

 <span data-ttu-id="7a780-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="7a780-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7a780-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="7a780-110">Child Elements</span></span>  
  
|<span data-ttu-id="7a780-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="7a780-111">Element</span></span>|<span data-ttu-id="7a780-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="7a780-112">Description</span></span>|  
|-------------|-----------------|  
|[\<oidEntry>](oidentry-element.md)|<span data-ttu-id="7a780-113">Asigna un OID ASN. 1 a un nombre descriptivo.</span><span class="sxs-lookup"><span data-stu-id="7a780-113">Maps an ASN.1 OID to a friendly name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7a780-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="7a780-114">Parent Elements</span></span>  
  
|<span data-ttu-id="7a780-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="7a780-115">Element</span></span>|<span data-ttu-id="7a780-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="7a780-116">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="7a780-117">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7a780-117">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="7a780-118">Contiene la configuración de criptografía.</span><span class="sxs-lookup"><span data-stu-id="7a780-118">Contains cryptography settings.</span></span>|  
|`mscorlib`|<span data-ttu-id="7a780-119">Contiene el `cryptographySettings` elemento.</span><span class="sxs-lookup"><span data-stu-id="7a780-119">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7a780-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7a780-120">Example</span></span>  

 <span data-ttu-id="7a780-121">En el ejemplo siguiente se muestra cómo usar el **\<oidMap>** elemento para que contenga una asignación de un OID para el algoritmo hash RIPEMD-160 a una implementación de ese algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="7a780-121">The following example shows how to use the **\<oidMap>** element to contain a mapping of an OID for the RIPEMD-160 hash algorithm to an implementation of that hash algorithm.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7a780-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="7a780-122">See also</span></span>

- [<span data-ttu-id="7a780-123">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="7a780-123">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="7a780-124">Esquema de configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="7a780-124">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="7a780-125">servicios criptográficos</span><span class="sxs-lookup"><span data-stu-id="7a780-125">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="7a780-126">Configurar clases de criptografía</span><span class="sxs-lookup"><span data-stu-id="7a780-126">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
- [<span data-ttu-id="7a780-127">Asignar identificadores de objeto a algoritmos de criptografía</span><span class="sxs-lookup"><span data-stu-id="7a780-127">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../map-object-identifiers-to-cryptography-algorithms.md)
