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
ms.openlocfilehash: 0215851f83a13ee48547144f08c5c693ec2d90bf
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91149535"
---
# <a name="cryptography-settings-schema"></a><span data-ttu-id="dfed0-102">Esquema de la configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="dfed0-102">Cryptography Settings Schema</span></span>

<span data-ttu-id="dfed0-103">El esquema de la configuración de criptografía contiene elementos que especifican cómo asignar nombres de algoritmo descriptivos a las clases que implementan algoritmos criptográficos.</span><span class="sxs-lookup"><span data-stu-id="dfed0-103">The cryptography settings schema contains elements that specify how to map friendly algorithm names to classes that implement cryptography algorithms.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoClasses>**](cryptoclasses-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoClass>**](cryptoclass-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<nameEntry>**](nameentry-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oidMap>**](oidmap-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oidEntry>**](oidentry-element.md)

|<span data-ttu-id="dfed0-104">Elemento</span><span class="sxs-lookup"><span data-stu-id="dfed0-104">Element</span></span>|<span data-ttu-id="dfed0-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="dfed0-105">Description</span></span>|  
|-------------|-----------------|  
|[**\<cryptoClasses**>](cryptoclasses-element.md)|<span data-ttu-id="dfed0-106">Contiene una lista de las clases de criptografía que tienen una asignación a un nombre descriptivo en el **\<nameEntry>** elemento.</span><span class="sxs-lookup"><span data-stu-id="dfed0-106">Contains a list of cryptography classes that have a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|[**\<cryptoClass**>](cryptoclass-element.md)|<span data-ttu-id="dfed0-107">Contiene una clase de criptografía que tiene una asignación a un nombre descriptivo en el **\<nameEntry>** elemento.</span><span class="sxs-lookup"><span data-stu-id="dfed0-107">Contains a cryptography class that has a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|[**\<cryptographySettings**>](cryptographysettings-element.md)|<span data-ttu-id="dfed0-108">Contiene la configuración de criptografía.</span><span class="sxs-lookup"><span data-stu-id="dfed0-108">Contains cryptography settings.</span></span>|  
|[**\<cryptoNameMapping**>](cryptonamemapping-element.md)|<span data-ttu-id="dfed0-109">Contiene asignaciones de clases a nombres descriptivos.</span><span class="sxs-lookup"><span data-stu-id="dfed0-109">Contains mappings of classes to friendly names.</span></span>|  
|[<span data-ttu-id="dfed0-110">**\<mscorlib>** elemento para la configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="dfed0-110">**\<mscorlib>** element for cryptography settings</span></span>](mscorlib-element-for-cryptography-settings.md)|<span data-ttu-id="dfed0-111">Contiene el **\<cryptographySettings>** elemento.</span><span class="sxs-lookup"><span data-stu-id="dfed0-111">Contains the **\<cryptographySettings>** element.</span></span>|  
|[**\<nameEntry>**](nameentry-element.md)|<span data-ttu-id="dfed0-112">Asigna un nombre de clase a un nombre de algoritmo descriptivo, que permite que una clase tenga varios nombres descriptivos.</span><span class="sxs-lookup"><span data-stu-id="dfed0-112">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>|  
|[**\<oidEntry>**](oidentry-element.md)|<span data-ttu-id="dfed0-113">Asigna un identificador de objeto (OID) ASN.1 a un nombre descriptivo.</span><span class="sxs-lookup"><span data-stu-id="dfed0-113">Maps an ASN.1 object identifier (OID) to a friendly name.</span></span>|  
|[**\<oidMap>**](oidmap-element.md)|<span data-ttu-id="dfed0-114">Contiene asignaciones de OID ASN.1 a clases.</span><span class="sxs-lookup"><span data-stu-id="dfed0-114">Contains ASN.1 OID mappings to classes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dfed0-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="dfed0-115">See also</span></span>

- [<span data-ttu-id="dfed0-116">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="dfed0-116">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="dfed0-117">servicios criptográficos</span><span class="sxs-lookup"><span data-stu-id="dfed0-117">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
