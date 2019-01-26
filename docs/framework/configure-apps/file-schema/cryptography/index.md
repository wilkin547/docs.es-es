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
ms.openlocfilehash: 2958ab01cb92872026437e31d2225d12d8606e97
ms.sourcegitcommit: b351b0781a035616c90c68ccae6dd60aae66a953
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2019
ms.locfileid: "55083384"
---
# <a name="cryptography-settings-schema"></a><span data-ttu-id="59f85-102">Esquema de la configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="59f85-102">Cryptography Settings Schema</span></span>
<span data-ttu-id="59f85-103">El esquema de la configuración de criptografía contiene elementos que especifican cómo asignar nombres de algoritmo descriptivos a las clases que implementan algoritmos criptográficos.</span><span class="sxs-lookup"><span data-stu-id="59f85-103">The cryptography settings schema contains elements that specify how to map friendly algorithm names to classes that implement cryptography algorithms.</span></span>  
  
 [<span data-ttu-id="59f85-104">**\<configuration>**</span><span class="sxs-lookup"><span data-stu-id="59f85-104">**\<configuration>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [<span data-ttu-id="59f85-105">**\<mscorlib>**</span><span class="sxs-lookup"><span data-stu-id="59f85-105">**\<mscorlib>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/mscorlib-element-for-cryptography-settings.md)  
  
 [<span data-ttu-id="59f85-106">**\<cryptographySettings>**</span><span class="sxs-lookup"><span data-stu-id="59f85-106">**\<cryptographySettings>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md)  
  
 [<span data-ttu-id="59f85-107">**\<cryptoNameMapping>**</span><span class="sxs-lookup"><span data-stu-id="59f85-107">**\<cryptoNameMapping>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptonamemapping-element.md)  
  
 [<span data-ttu-id="59f85-108">**\<cryptoClasses>**</span><span class="sxs-lookup"><span data-stu-id="59f85-108">**\<cryptoClasses>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclasses-element.md)  
  
 [<span data-ttu-id="59f85-109">**\<cryptoClass>**</span><span class="sxs-lookup"><span data-stu-id="59f85-109">**\<cryptoClass>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md)  
  
 [<span data-ttu-id="59f85-110">**\<nameEntry>**</span><span class="sxs-lookup"><span data-stu-id="59f85-110">**\<nameEntry>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md)  
  
 [<span data-ttu-id="59f85-111">**\<oidMap>**</span><span class="sxs-lookup"><span data-stu-id="59f85-111">**\<oidMap>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidmap-element.md)  
  
 [<span data-ttu-id="59f85-112">**\<oidEntry>**</span><span class="sxs-lookup"><span data-stu-id="59f85-112">**\<oidEntry>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md)  
  
|<span data-ttu-id="59f85-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="59f85-113">Element</span></span>|<span data-ttu-id="59f85-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="59f85-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="59f85-115">**\<cryptoClasses**></span><span class="sxs-lookup"><span data-stu-id="59f85-115">**\<cryptoClasses**></span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclasses-element.md)|<span data-ttu-id="59f85-116">Contiene una lista de las clases de criptografía que tienen una asignación a un nombre descriptivo en el elemento **\<nameEntry>**.</span><span class="sxs-lookup"><span data-stu-id="59f85-116">Contains a list of cryptography classes that have a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|[<span data-ttu-id="59f85-117">**\<cryptoClass**></span><span class="sxs-lookup"><span data-stu-id="59f85-117">**\<cryptoClass**></span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md)|<span data-ttu-id="59f85-118">Contiene una clase de criptografía que tiene una asignación a un nombre descriptivo en el elemento **\<nameEntry>**.</span><span class="sxs-lookup"><span data-stu-id="59f85-118">Contains a cryptography class that has a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|[<span data-ttu-id="59f85-119">**\<cryptographySettings**></span><span class="sxs-lookup"><span data-stu-id="59f85-119">**\<cryptographySettings**></span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md)|<span data-ttu-id="59f85-120">Contiene la configuración de criptografía.</span><span class="sxs-lookup"><span data-stu-id="59f85-120">Contains cryptography settings.</span></span>|  
|[<span data-ttu-id="59f85-121">**\<cryptoNameMapping**></span><span class="sxs-lookup"><span data-stu-id="59f85-121">**\<cryptoNameMapping**></span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptonamemapping-element.md)|<span data-ttu-id="59f85-122">Contiene asignaciones de clases a nombres descriptivos.</span><span class="sxs-lookup"><span data-stu-id="59f85-122">Contains mappings of classes to friendly names.</span></span>|  
|[<span data-ttu-id="59f85-123">Elemento **\<mscorlib>** para la configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="59f85-123">**\<mscorlib>** element for cryptography settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/mscorlib-element-for-cryptography-settings.md)|<span data-ttu-id="59f85-124">Contiene el elemento **\<cryptographySettings>**.</span><span class="sxs-lookup"><span data-stu-id="59f85-124">Contains the **\<cryptographySettings>** element.</span></span>|  
|[<span data-ttu-id="59f85-125">**\<nameEntry>**</span><span class="sxs-lookup"><span data-stu-id="59f85-125">**\<nameEntry>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md)|<span data-ttu-id="59f85-126">Asigna un nombre de clase a un nombre de algoritmo descriptivo, que permite que una clase tenga varios nombres descriptivos.</span><span class="sxs-lookup"><span data-stu-id="59f85-126">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>|  
|[<span data-ttu-id="59f85-127">**\<oidEntry>**</span><span class="sxs-lookup"><span data-stu-id="59f85-127">**\<oidEntry>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md)|<span data-ttu-id="59f85-128">Asigna un identificador de objeto (OID) ASN.1 a un nombre descriptivo.</span><span class="sxs-lookup"><span data-stu-id="59f85-128">Maps an ASN.1 object identifier (OID) to a friendly name.</span></span>|  
|[<span data-ttu-id="59f85-129">**\<oidMap>**</span><span class="sxs-lookup"><span data-stu-id="59f85-129">**\<oidMap>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidmap-element.md)|<span data-ttu-id="59f85-130">Contiene asignaciones de OID ASN.1 a clases.</span><span class="sxs-lookup"><span data-stu-id="59f85-130">Contains ASN.1 OID mappings to classes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="59f85-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="59f85-131">See also</span></span>
- [<span data-ttu-id="59f85-132">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="59f85-132">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="59f85-133">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="59f85-133">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)
