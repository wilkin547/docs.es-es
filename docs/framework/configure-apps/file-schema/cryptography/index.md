---
description: 'Más información acerca de: esquema de configuración de criptografía'
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
ms.openlocfilehash: a7b3c020ed760aba24c9faf020281b7ad4bf3af7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99730088"
---
# <a name="cryptography-settings-schema"></a><span data-ttu-id="2b077-103">Esquema de la configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="2b077-103">Cryptography Settings Schema</span></span>

<span data-ttu-id="2b077-104">El esquema de la configuración de criptografía contiene elementos que especifican cómo asignar nombres de algoritmo descriptivos a las clases que implementan algoritmos criptográficos.</span><span class="sxs-lookup"><span data-stu-id="2b077-104">The cryptography settings schema contains elements that specify how to map friendly algorithm names to classes that implement cryptography algorithms.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoClasses>**](cryptoclasses-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoClass>**](cryptoclass-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<nameEntry>**](nameentry-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oidMap>**](oidmap-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oidEntry>**](oidentry-element.md)

|<span data-ttu-id="2b077-105">Elemento</span><span class="sxs-lookup"><span data-stu-id="2b077-105">Element</span></span>|<span data-ttu-id="2b077-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="2b077-106">Description</span></span>|  
|-------------|-----------------|  
|[**\<cryptoClasses**>](cryptoclasses-element.md)|<span data-ttu-id="2b077-107">Contiene una lista de las clases de criptografía que tienen una asignación a un nombre descriptivo en el **\<nameEntry>** elemento.</span><span class="sxs-lookup"><span data-stu-id="2b077-107">Contains a list of cryptography classes that have a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|[**\<cryptoClass**>](cryptoclass-element.md)|<span data-ttu-id="2b077-108">Contiene una clase de criptografía que tiene una asignación a un nombre descriptivo en el **\<nameEntry>** elemento.</span><span class="sxs-lookup"><span data-stu-id="2b077-108">Contains a cryptography class that has a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|[**\<cryptographySettings**>](cryptographysettings-element.md)|<span data-ttu-id="2b077-109">Contiene la configuración de criptografía.</span><span class="sxs-lookup"><span data-stu-id="2b077-109">Contains cryptography settings.</span></span>|  
|[**\<cryptoNameMapping**>](cryptonamemapping-element.md)|<span data-ttu-id="2b077-110">Contiene asignaciones de clases a nombres descriptivos.</span><span class="sxs-lookup"><span data-stu-id="2b077-110">Contains mappings of classes to friendly names.</span></span>|  
|[<span data-ttu-id="2b077-111">**\<mscorlib>** elemento para la configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="2b077-111">**\<mscorlib>** element for cryptography settings</span></span>](mscorlib-element-for-cryptography-settings.md)|<span data-ttu-id="2b077-112">Contiene el **\<cryptographySettings>** elemento.</span><span class="sxs-lookup"><span data-stu-id="2b077-112">Contains the **\<cryptographySettings>** element.</span></span>|  
|[**\<nameEntry>**](nameentry-element.md)|<span data-ttu-id="2b077-113">Asigna un nombre de clase a un nombre de algoritmo descriptivo, que permite que una clase tenga varios nombres descriptivos.</span><span class="sxs-lookup"><span data-stu-id="2b077-113">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>|  
|[**\<oidEntry>**](oidentry-element.md)|<span data-ttu-id="2b077-114">Asigna un identificador de objeto (OID) ASN.1 a un nombre descriptivo.</span><span class="sxs-lookup"><span data-stu-id="2b077-114">Maps an ASN.1 object identifier (OID) to a friendly name.</span></span>|  
|[**\<oidMap>**](oidmap-element.md)|<span data-ttu-id="2b077-115">Contiene asignaciones de OID ASN.1 a clases.</span><span class="sxs-lookup"><span data-stu-id="2b077-115">Contains ASN.1 OID mappings to classes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2b077-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="2b077-116">See also</span></span>

- [<span data-ttu-id="2b077-117">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="2b077-117">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="2b077-118">servicios criptográficos</span><span class="sxs-lookup"><span data-stu-id="2b077-118">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
