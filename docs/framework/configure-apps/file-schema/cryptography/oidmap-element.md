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
ms.openlocfilehash: eec2c4745ad5a0492ccf04c8f23b901275f23c01
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698444"
---
# <a name="oidmap-element"></a><span data-ttu-id="10874-102">\<oidMap >, elemento</span><span class="sxs-lookup"><span data-stu-id="10874-102">\<oidMap> Element</span></span>
<span data-ttu-id="10874-103">Contiene las asignaciones de identificador de objetos (OID) ASN. 1 a las clases.</span><span class="sxs-lookup"><span data-stu-id="10874-103">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>  
  
[<span data-ttu-id="10874-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="10874-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="10874-105">&nbsp; @ no__t-1[ **\<mscorlib >** ](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="10874-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>  
<span data-ttu-id="10874-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<cryptographySettings >** ](cryptographysettings-element.md)</span><span class="sxs-lookup"><span data-stu-id="10874-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)</span></span>  
<span data-ttu-id="10874-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<oidMap >**</span><span class="sxs-lookup"><span data-stu-id="10874-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<oidMap>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10874-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="10874-108">Syntax</span></span>  
  
```xml  
<oidMap>   
</oidMap>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="10874-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="10874-109">Attributes and Elements</span></span>  
 <span data-ttu-id="10874-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="10874-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="10874-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="10874-111">Attributes</span></span>  
 <span data-ttu-id="10874-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="10874-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="10874-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="10874-113">Child Elements</span></span>  
  
|<span data-ttu-id="10874-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="10874-114">Element</span></span>|<span data-ttu-id="10874-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="10874-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="10874-116">\<oidEntry></span><span class="sxs-lookup"><span data-stu-id="10874-116">\<oidEntry></span></span>](oidentry-element.md)|<span data-ttu-id="10874-117">Asigna un OID ASN. 1 a un nombre descriptivo.</span><span class="sxs-lookup"><span data-stu-id="10874-117">Maps an ASN.1 OID to a friendly name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="10874-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="10874-118">Parent Elements</span></span>  
  
|<span data-ttu-id="10874-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="10874-119">Element</span></span>|<span data-ttu-id="10874-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="10874-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="10874-121">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="10874-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="10874-122">Contiene la configuración de criptografía.</span><span class="sxs-lookup"><span data-stu-id="10874-122">Contains cryptography settings.</span></span>|  
|`mscorlib`|<span data-ttu-id="10874-123">Contiene el `cryptographySettings` elemento.</span><span class="sxs-lookup"><span data-stu-id="10874-123">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="10874-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="10874-124">Example</span></span>  
 <span data-ttu-id="10874-125">En el ejemplo siguiente se muestra cómo usar el elemento **@no__t >** para que contenga una asignación de un OID para el algoritmo hash RIPEMD-160 a una implementación de ese algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="10874-125">The following example shows how to use the **\<oidMap>** element to contain a mapping of an OID for the RIPEMD-160 hash algorithm to an implementation of that hash algorithm.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="10874-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="10874-126">See also</span></span>

- [<span data-ttu-id="10874-127">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="10874-127">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="10874-128">Esquema de la configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="10874-128">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="10874-129">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="10874-129">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="10874-130">Configurar clases de criptografía</span><span class="sxs-lookup"><span data-stu-id="10874-130">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
- [<span data-ttu-id="10874-131">Asignar identificadores de objeto a algoritmos de criptografía</span><span class="sxs-lookup"><span data-stu-id="10874-131">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../map-object-identifiers-to-cryptography-algorithms.md)
