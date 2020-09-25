---
title: <cryptographySettings> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptographySettings
helpviewer_keywords:
- cryptographySettings element
- <cryptographySettings> element
ms.assetid: 6201b7da-bcb7-49f7-b9f5-ba1fe05573b9
ms.openlocfilehash: 3c3513c05485550202f2fc5bcae1faabb0e75d47
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201816"
---
# <a name="cryptographysettings-element"></a><span data-ttu-id="02791-102">\<cryptographySettings> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="02791-102">\<cryptographySettings> Element</span></span>

<span data-ttu-id="02791-103">Contiene la configuración de criptografía.</span><span class="sxs-lookup"><span data-stu-id="02791-103">Contains cryptography settings.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptographySettings>**

## <a name="syntax"></a><span data-ttu-id="02791-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="02791-104">Syntax</span></span>  
  
```xml  
      <cryptographySettings>
</cryptographySettings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="02791-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="02791-105">Attributes and Elements</span></span>  

 <span data-ttu-id="02791-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="02791-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="02791-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="02791-107">Attributes</span></span>  

 <span data-ttu-id="02791-108">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="02791-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="02791-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="02791-109">Child Elements</span></span>  
  
|<span data-ttu-id="02791-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="02791-110">Element</span></span>|<span data-ttu-id="02791-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="02791-111">Description</span></span>|  
|-------------|-----------------|  
|[\<cryptoNameMapping>](cryptonamemapping-element.md)|<span data-ttu-id="02791-112">Contiene asignaciones de clases a nombres descriptivos.</span><span class="sxs-lookup"><span data-stu-id="02791-112">Contains mappings of classes to friendly names.</span></span>|  
|[\<oidMap>](oidmap-element.md)|<span data-ttu-id="02791-113">Contiene las asignaciones de identificador de objetos (OID) ASN. 1 a las clases.</span><span class="sxs-lookup"><span data-stu-id="02791-113">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="02791-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="02791-114">Parent Elements</span></span>  
  
|<span data-ttu-id="02791-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="02791-115">Element</span></span>|<span data-ttu-id="02791-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="02791-116">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="02791-117">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="02791-117">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`mscorlib`|<span data-ttu-id="02791-118">Contiene el `cryptographySettings` elemento.</span><span class="sxs-lookup"><span data-stu-id="02791-118">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="02791-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="02791-119">Example</span></span>  

 <span data-ttu-id="02791-120">En el ejemplo siguiente se muestra cómo usar el **\<cryptographySettings>** elemento para contener asignaciones de nombres de criptografía y asignaciones de OID.</span><span class="sxs-lookup"><span data-stu-id="02791-120">The following example shows how use the **\<cryptographySettings>** element to contain cryptography name mappings and OID mappings.</span></span> <span data-ttu-id="02791-121">En este ejemplo se configura el tiempo de ejecución para que <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> devuelva un `MyHashClass` objeto y la `MyCryptoClass` clase se asigne al identificador de objeto 1.3.36.2.1.</span><span class="sxs-lookup"><span data-stu-id="02791-121">This example configures the runtime so that <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> returns a `MyHashClass` object and the `MyCryptoClass` class maps to the object identifier 1.3.36.2.1.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyHash="MyHashClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
               <cryptoClass   MyCrypto="MyCryptoClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="System.Security.Cryptography.HashAlgorithm"  
                       class="MyHash"/>  
         </cryptoNameMapping>  
         <oidMap>  
            <oidEntry OID="1.3.36.3.2.1"   name="MyCryptoClass"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="02791-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="02791-122">See also</span></span>

- [<span data-ttu-id="02791-123">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="02791-123">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="02791-124">Esquema de configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="02791-124">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="02791-125">servicios criptográficos</span><span class="sxs-lookup"><span data-stu-id="02791-125">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
