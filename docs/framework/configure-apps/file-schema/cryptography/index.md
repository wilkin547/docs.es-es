---
title: Esquema de la configuración de criptografía
ms.date: 03/30/2017
helpviewer_keywords:
- configuration schema [.NET Framework], cryptography
- elements [.NET Framework], cryptography
- schema configuration settings
- cryptography, settings schema
- cryptography, mapping algorithm names
- configuration sections [.NET Framework]
- configuration settings [.NET Framework], cryptography
ms.assetid: 1f55050a-b2a3-4868-a3c0-da20826150f3
ms.openlocfilehash: 474c3274bfba6803ebb17289f138251d755250e4
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699799"
---
# <a name="cryptography-settings-schema"></a><span data-ttu-id="5ac94-102">Esquema de la configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="5ac94-102">Cryptography Settings Schema</span></span>
<span data-ttu-id="5ac94-103">El esquema de la configuración de criptografía contiene elementos que especifican cómo asignar nombres de algoritmo descriptivos a las clases que implementan algoritmos criptográficos.</span><span class="sxs-lookup"><span data-stu-id="5ac94-103">The cryptography settings schema contains elements that specify how to map friendly algorithm names to classes that implement cryptography algorithms.</span></span>  
  
[<span data-ttu-id="5ac94-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="5ac94-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="5ac94-105">&nbsp; @ no__t-1[ **\<mscorlib >** ](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="5ac94-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>  
<span data-ttu-id="5ac94-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<cryptographySettings >** ](cryptographysettings-element.md)</span><span class="sxs-lookup"><span data-stu-id="5ac94-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)</span></span>  
<span data-ttu-id="5ac94-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5[ **\<cryptoNameMapping >** ](cryptonamemapping-element.md)</span><span class="sxs-lookup"><span data-stu-id="5ac94-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)</span></span>  
<span data-ttu-id="5ac94-108">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7[ **&nbsp;0cryptoClasses >** ](cryptoclasses-element.md)</span><span class="sxs-lookup"><span data-stu-id="5ac94-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoClasses>**](cryptoclasses-element.md)</span></span>  
<span data-ttu-id="5ac94-109">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7 @ no__t-8 @ no__t-9[ **&nbsp;2cryptoClass >** ](cryptoclass-element.md)</span><span class="sxs-lookup"><span data-stu-id="5ac94-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoClass>**](cryptoclass-element.md)</span></span>  
<span data-ttu-id="5ac94-110">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7[ **&nbsp;0nameEntry >** ](nameentry-element.md)</span><span class="sxs-lookup"><span data-stu-id="5ac94-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<nameEntry>**](nameentry-element.md)</span></span>  
<span data-ttu-id="5ac94-111">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5[ **\<oidMap >** ](oidmap-element.md)</span><span class="sxs-lookup"><span data-stu-id="5ac94-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oidMap>**](oidmap-element.md)</span></span>  
<span data-ttu-id="5ac94-112">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6[ **\<oidEntry >** ](oidentry-element.md)</span><span class="sxs-lookup"><span data-stu-id="5ac94-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oidEntry>**](oidentry-element.md)</span></span>  
  
|<span data-ttu-id="5ac94-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="5ac94-113">Element</span></span>|<span data-ttu-id="5ac94-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="5ac94-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5ac94-115"> **\<cryptoClasses**></span><span class="sxs-lookup"><span data-stu-id="5ac94-115">**\<cryptoClasses**></span></span>](cryptoclasses-element.md)|<span data-ttu-id="5ac94-116">Contiene una lista de las clases de criptografía que tienen una asignación a un nombre descriptivo en el elemento **\<nameEntry>** .</span><span class="sxs-lookup"><span data-stu-id="5ac94-116">Contains a list of cryptography classes that have a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|[<span data-ttu-id="5ac94-117"> **\<cryptoClass**></span><span class="sxs-lookup"><span data-stu-id="5ac94-117">**\<cryptoClass**></span></span>](cryptoclass-element.md)|<span data-ttu-id="5ac94-118">Contiene una clase de criptografía que tiene una asignación a un nombre descriptivo en el elemento **\<nameEntry>** .</span><span class="sxs-lookup"><span data-stu-id="5ac94-118">Contains a cryptography class that has a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|[<span data-ttu-id="5ac94-119"> **\<cryptographySettings**></span><span class="sxs-lookup"><span data-stu-id="5ac94-119">**\<cryptographySettings**></span></span>](cryptographysettings-element.md)|<span data-ttu-id="5ac94-120">Contiene la configuración de criptografía.</span><span class="sxs-lookup"><span data-stu-id="5ac94-120">Contains cryptography settings.</span></span>|  
|[<span data-ttu-id="5ac94-121"> **\<cryptoNameMapping**></span><span class="sxs-lookup"><span data-stu-id="5ac94-121">**\<cryptoNameMapping**></span></span>](cryptonamemapping-element.md)|<span data-ttu-id="5ac94-122">Contiene asignaciones de clases a nombres descriptivos.</span><span class="sxs-lookup"><span data-stu-id="5ac94-122">Contains mappings of classes to friendly names.</span></span>|  
|[<span data-ttu-id="5ac94-123">Elemento **\<mscorlib>** para la configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="5ac94-123">**\<mscorlib>** element for cryptography settings</span></span>](mscorlib-element-for-cryptography-settings.md)|<span data-ttu-id="5ac94-124">Contiene el elemento **\<cryptographySettings>** .</span><span class="sxs-lookup"><span data-stu-id="5ac94-124">Contains the **\<cryptographySettings>** element.</span></span>|  
|[<span data-ttu-id="5ac94-125"> **\<nameEntry>** </span><span class="sxs-lookup"><span data-stu-id="5ac94-125">**\<nameEntry>**</span></span>](nameentry-element.md)|<span data-ttu-id="5ac94-126">Asigna un nombre de clase a un nombre de algoritmo descriptivo, que permite que una clase tenga varios nombres descriptivos.</span><span class="sxs-lookup"><span data-stu-id="5ac94-126">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>|  
|[<span data-ttu-id="5ac94-127"> **\<oidEntry>** </span><span class="sxs-lookup"><span data-stu-id="5ac94-127">**\<oidEntry>**</span></span>](oidentry-element.md)|<span data-ttu-id="5ac94-128">Asigna un identificador de objeto (OID) ASN.1 a un nombre descriptivo.</span><span class="sxs-lookup"><span data-stu-id="5ac94-128">Maps an ASN.1 object identifier (OID) to a friendly name.</span></span>|  
|[<span data-ttu-id="5ac94-129"> **\<oidMap>** </span><span class="sxs-lookup"><span data-stu-id="5ac94-129">**\<oidMap>**</span></span>](oidmap-element.md)|<span data-ttu-id="5ac94-130">Contiene asignaciones de OID ASN.1 a clases.</span><span class="sxs-lookup"><span data-stu-id="5ac94-130">Contains ASN.1 OID mappings to classes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5ac94-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="5ac94-131">See also</span></span>

- [<span data-ttu-id="5ac94-132">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="5ac94-132">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="5ac94-133">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="5ac94-133">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
