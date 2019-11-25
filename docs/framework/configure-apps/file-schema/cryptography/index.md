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
ms.openlocfilehash: c632a15552c8ba5743aac1309098b7d7ef949bbd
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088006"
---
# <a name="cryptography-settings-schema"></a><span data-ttu-id="f2223-102">Esquema de la configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="f2223-102">Cryptography Settings Schema</span></span>
<span data-ttu-id="f2223-103">El esquema de la configuración de criptografía contiene elementos que especifican cómo asignar nombres de algoritmo descriptivos a las clases que implementan algoritmos criptográficos.</span><span class="sxs-lookup"><span data-stu-id="f2223-103">The cryptography settings schema contains elements that specify how to map friendly algorithm names to classes that implement cryptography algorithms.</span></span>  
  
<span data-ttu-id="f2223-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f2223-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f2223-105">&nbsp;&nbsp;[ **\<mscorlib >** ](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="f2223-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>\
<span data-ttu-id="f2223-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<cryptographySettings >** ](cryptographysettings-element.md)</span><span class="sxs-lookup"><span data-stu-id="f2223-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)</span></span>\
<span data-ttu-id="f2223-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<cryptoNameMapping**](cryptonamemapping-element.md) ></span><span class="sxs-lookup"><span data-stu-id="f2223-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)</span></span>\
<span data-ttu-id="f2223-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<cryptoClasses**](cryptoclasses-element.md) ></span><span class="sxs-lookup"><span data-stu-id="f2223-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoClasses>**](cryptoclasses-element.md)</span></span>\
<span data-ttu-id="f2223-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<cryptoClass >** ](cryptoclass-element.md)</span><span class="sxs-lookup"><span data-stu-id="f2223-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoClass>**](cryptoclass-element.md)</span></span>\
<span data-ttu-id="f2223-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<elemento nameEntry**](nameentry-element.md) ></span><span class="sxs-lookup"><span data-stu-id="f2223-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<nameEntry>**](nameentry-element.md)</span></span>\
<span data-ttu-id="f2223-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<oidMap**](oidmap-element.md) ></span><span class="sxs-lookup"><span data-stu-id="f2223-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oidMap>**](oidmap-element.md)</span></span>\
<span data-ttu-id="f2223-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<oidEntry >** ](oidentry-element.md)</span><span class="sxs-lookup"><span data-stu-id="f2223-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oidEntry>**](oidentry-element.md)</span></span>

|<span data-ttu-id="f2223-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="f2223-113">Element</span></span>|<span data-ttu-id="f2223-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="f2223-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f2223-115"> **\<cryptoClasses**></span><span class="sxs-lookup"><span data-stu-id="f2223-115">**\<cryptoClasses**></span></span>](cryptoclasses-element.md)|<span data-ttu-id="f2223-116">Contiene una lista de las clases de criptografía que tienen una asignación a un nombre descriptivo en el elemento **\<nameEntry>** .</span><span class="sxs-lookup"><span data-stu-id="f2223-116">Contains a list of cryptography classes that have a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|[<span data-ttu-id="f2223-117"> **\<cryptoClass**></span><span class="sxs-lookup"><span data-stu-id="f2223-117">**\<cryptoClass**></span></span>](cryptoclass-element.md)|<span data-ttu-id="f2223-118">Contiene una clase de criptografía que tiene una asignación a un nombre descriptivo en el elemento **\<nameEntry>** .</span><span class="sxs-lookup"><span data-stu-id="f2223-118">Contains a cryptography class that has a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|[<span data-ttu-id="f2223-119"> **\<cryptographySettings**></span><span class="sxs-lookup"><span data-stu-id="f2223-119">**\<cryptographySettings**></span></span>](cryptographysettings-element.md)|<span data-ttu-id="f2223-120">Contiene la configuración de criptografía.</span><span class="sxs-lookup"><span data-stu-id="f2223-120">Contains cryptography settings.</span></span>|  
|[<span data-ttu-id="f2223-121"> **\<cryptoNameMapping**></span><span class="sxs-lookup"><span data-stu-id="f2223-121">**\<cryptoNameMapping**></span></span>](cryptonamemapping-element.md)|<span data-ttu-id="f2223-122">Contiene asignaciones de clases a nombres descriptivos.</span><span class="sxs-lookup"><span data-stu-id="f2223-122">Contains mappings of classes to friendly names.</span></span>|  
|[<span data-ttu-id="f2223-123">Elemento **\<mscorlib>** para la configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="f2223-123">**\<mscorlib>** element for cryptography settings</span></span>](mscorlib-element-for-cryptography-settings.md)|<span data-ttu-id="f2223-124">Contiene el elemento **\<cryptographySettings>** .</span><span class="sxs-lookup"><span data-stu-id="f2223-124">Contains the **\<cryptographySettings>** element.</span></span>|  
|[<span data-ttu-id="f2223-125"> **\<nameEntry>** </span><span class="sxs-lookup"><span data-stu-id="f2223-125">**\<nameEntry>**</span></span>](nameentry-element.md)|<span data-ttu-id="f2223-126">Asigna un nombre de clase a un nombre de algoritmo descriptivo, que permite que una clase tenga varios nombres descriptivos.</span><span class="sxs-lookup"><span data-stu-id="f2223-126">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>|  
|[<span data-ttu-id="f2223-127"> **\<oidEntry>** </span><span class="sxs-lookup"><span data-stu-id="f2223-127">**\<oidEntry>**</span></span>](oidentry-element.md)|<span data-ttu-id="f2223-128">Asigna un identificador de objeto (OID) ASN.1 a un nombre descriptivo.</span><span class="sxs-lookup"><span data-stu-id="f2223-128">Maps an ASN.1 object identifier (OID) to a friendly name.</span></span>|  
|[<span data-ttu-id="f2223-129"> **\<oidMap>** </span><span class="sxs-lookup"><span data-stu-id="f2223-129">**\<oidMap>**</span></span>](oidmap-element.md)|<span data-ttu-id="f2223-130">Contiene asignaciones de OID ASN.1 a clases.</span><span class="sxs-lookup"><span data-stu-id="f2223-130">Contains ASN.1 OID mappings to classes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f2223-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="f2223-131">See also</span></span>

- [<span data-ttu-id="f2223-132">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="f2223-132">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="f2223-133">Servicios criptográficos</span><span class="sxs-lookup"><span data-stu-id="f2223-133">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
