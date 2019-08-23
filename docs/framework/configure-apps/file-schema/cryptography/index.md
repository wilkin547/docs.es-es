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
ms.openlocfilehash: a7964d01905be4e3dd6e8149e5533e9a2cfd9a71
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927632"
---
# <a name="cryptography-settings-schema"></a><span data-ttu-id="46851-102">Esquema de la configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="46851-102">Cryptography Settings Schema</span></span>
<span data-ttu-id="46851-103">El esquema de la configuración de criptografía contiene elementos que especifican cómo asignar nombres de algoritmo descriptivos a las clases que implementan algoritmos criptográficos.</span><span class="sxs-lookup"><span data-stu-id="46851-103">The cryptography settings schema contains elements that specify how to map friendly algorithm names to classes that implement cryptography algorithms.</span></span>  
  
 [<span data-ttu-id="46851-104">**\<configuration>**</span><span class="sxs-lookup"><span data-stu-id="46851-104">**\<configuration>**</span></span>](../configuration-element.md)  
  
 [<span data-ttu-id="46851-105">**\<mscorlib>**</span><span class="sxs-lookup"><span data-stu-id="46851-105">**\<mscorlib>**</span></span>](mscorlib-element-for-cryptography-settings.md)  
  
 [<span data-ttu-id="46851-106">**\<cryptographySettings>**</span><span class="sxs-lookup"><span data-stu-id="46851-106">**\<cryptographySettings>**</span></span>](cryptographysettings-element.md)  
  
 [<span data-ttu-id="46851-107">**\<cryptoNameMapping>**</span><span class="sxs-lookup"><span data-stu-id="46851-107">**\<cryptoNameMapping>**</span></span>](cryptonamemapping-element.md)  
  
 [<span data-ttu-id="46851-108">**\<cryptoClasses>**</span><span class="sxs-lookup"><span data-stu-id="46851-108">**\<cryptoClasses>**</span></span>](cryptoclasses-element.md)  
  
 [<span data-ttu-id="46851-109">**\<cryptoClass>**</span><span class="sxs-lookup"><span data-stu-id="46851-109">**\<cryptoClass>**</span></span>](cryptoclass-element.md)  
  
 [<span data-ttu-id="46851-110">**\<nameEntry>**</span><span class="sxs-lookup"><span data-stu-id="46851-110">**\<nameEntry>**</span></span>](nameentry-element.md)  
  
 [<span data-ttu-id="46851-111">**\<oidMap>**</span><span class="sxs-lookup"><span data-stu-id="46851-111">**\<oidMap>**</span></span>](oidmap-element.md)  
  
 [<span data-ttu-id="46851-112">**\<oidEntry>**</span><span class="sxs-lookup"><span data-stu-id="46851-112">**\<oidEntry>**</span></span>](oidentry-element.md)  
  
|<span data-ttu-id="46851-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="46851-113">Element</span></span>|<span data-ttu-id="46851-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="46851-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="46851-115">**\<cryptoClasses**></span><span class="sxs-lookup"><span data-stu-id="46851-115">**\<cryptoClasses**></span></span>](cryptoclasses-element.md)|<span data-ttu-id="46851-116">Contiene una lista de las clases de criptografía que tienen una asignación a un nombre descriptivo en el elemento **\<nameEntry>**.</span><span class="sxs-lookup"><span data-stu-id="46851-116">Contains a list of cryptography classes that have a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|[<span data-ttu-id="46851-117">**\<cryptoClass**></span><span class="sxs-lookup"><span data-stu-id="46851-117">**\<cryptoClass**></span></span>](cryptoclass-element.md)|<span data-ttu-id="46851-118">Contiene una clase de criptografía que tiene una asignación a un nombre descriptivo en el elemento **\<nameEntry>**.</span><span class="sxs-lookup"><span data-stu-id="46851-118">Contains a cryptography class that has a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|[<span data-ttu-id="46851-119">**\<cryptographySettings**></span><span class="sxs-lookup"><span data-stu-id="46851-119">**\<cryptographySettings**></span></span>](cryptographysettings-element.md)|<span data-ttu-id="46851-120">Contiene la configuración de criptografía.</span><span class="sxs-lookup"><span data-stu-id="46851-120">Contains cryptography settings.</span></span>|  
|[<span data-ttu-id="46851-121">**\<cryptoNameMapping**></span><span class="sxs-lookup"><span data-stu-id="46851-121">**\<cryptoNameMapping**></span></span>](cryptonamemapping-element.md)|<span data-ttu-id="46851-122">Contiene asignaciones de clases a nombres descriptivos.</span><span class="sxs-lookup"><span data-stu-id="46851-122">Contains mappings of classes to friendly names.</span></span>|  
|[<span data-ttu-id="46851-123">Elemento **\<mscorlib>** para la configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="46851-123">**\<mscorlib>** element for cryptography settings</span></span>](mscorlib-element-for-cryptography-settings.md)|<span data-ttu-id="46851-124">Contiene el elemento **\<cryptographySettings>**.</span><span class="sxs-lookup"><span data-stu-id="46851-124">Contains the **\<cryptographySettings>** element.</span></span>|  
|[<span data-ttu-id="46851-125">**\<nameEntry>**</span><span class="sxs-lookup"><span data-stu-id="46851-125">**\<nameEntry>**</span></span>](nameentry-element.md)|<span data-ttu-id="46851-126">Asigna un nombre de clase a un nombre de algoritmo descriptivo, que permite que una clase tenga varios nombres descriptivos.</span><span class="sxs-lookup"><span data-stu-id="46851-126">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>|  
|[<span data-ttu-id="46851-127">**\<oidEntry>**</span><span class="sxs-lookup"><span data-stu-id="46851-127">**\<oidEntry>**</span></span>](oidentry-element.md)|<span data-ttu-id="46851-128">Asigna un identificador de objeto (OID) ASN.1 a un nombre descriptivo.</span><span class="sxs-lookup"><span data-stu-id="46851-128">Maps an ASN.1 object identifier (OID) to a friendly name.</span></span>|  
|[<span data-ttu-id="46851-129">**\<oidMap>**</span><span class="sxs-lookup"><span data-stu-id="46851-129">**\<oidMap>**</span></span>](oidmap-element.md)|<span data-ttu-id="46851-130">Contiene asignaciones de OID ASN.1 a clases.</span><span class="sxs-lookup"><span data-stu-id="46851-130">Contains ASN.1 OID mappings to classes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="46851-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="46851-131">See also</span></span>

- [<span data-ttu-id="46851-132">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="46851-132">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="46851-133">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="46851-133">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
