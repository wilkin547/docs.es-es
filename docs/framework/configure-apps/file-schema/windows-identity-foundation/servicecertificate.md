---
title: <serviceCertificate>
ms.date: 03/30/2017
ms.assetid: 42c7f291-2ec3-43c5-8872-35897ff3c660
author: BrucePerlerMS
ms.openlocfilehash: 653dd9cfadbfd33f5371b77172199b946321bc8c
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251856"
---
# <a name="servicecertificate"></a><span data-ttu-id="02b0d-101">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="02b0d-101">\<serviceCertificate></span></span>
<span data-ttu-id="02b0d-102">Configura el certificado X. 509 que se usa para cifrar y descifrar los tokens.</span><span class="sxs-lookup"><span data-stu-id="02b0d-102">Configures the X.509 certificate that is used to encrypt and decrypt tokens.</span></span>  
  
<span data-ttu-id="02b0d-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="02b0d-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="02b0d-104">&nbsp;&nbsp;[ **\<System. identityModel. Services >** ](system-identitymodel-services.md)</span><span class="sxs-lookup"><span data-stu-id="02b0d-104">&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)</span></span>\
<span data-ttu-id="02b0d-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> federationConfiguration**](federationconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="02b0d-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)</span></span>\
<span data-ttu-id="02b0d-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> serviceCertificate**</span><span class="sxs-lookup"><span data-stu-id="02b0d-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceCertificate>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02b0d-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="02b0d-107">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="02b0d-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="02b0d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="02b0d-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="02b0d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="02b0d-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="02b0d-110">Attributes</span></span>  
 <span data-ttu-id="02b0d-111">None</span><span class="sxs-lookup"><span data-stu-id="02b0d-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="02b0d-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="02b0d-112">Child Elements</span></span>  
  
|<span data-ttu-id="02b0d-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="02b0d-113">Element</span></span>|<span data-ttu-id="02b0d-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="02b0d-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="02b0d-115">\<certificateReference></span><span class="sxs-lookup"><span data-stu-id="02b0d-115">\<certificateReference></span></span>](certificatereference.md)|<span data-ttu-id="02b0d-116">Especifica los valores que se usan para buscar y validar un certificado X. 509 en un almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="02b0d-116">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="02b0d-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="02b0d-117">Parent Elements</span></span>  
  
|<span data-ttu-id="02b0d-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="02b0d-118">Element</span></span>|<span data-ttu-id="02b0d-119">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="02b0d-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="02b0d-120">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="02b0d-120">\<federationConfiguration></span></span>](federationconfiguration.md)|<span data-ttu-id="02b0d-121">Contiene la configuración que configura el <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) y el <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span><span class="sxs-lookup"><span data-stu-id="02b0d-121">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="02b0d-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="02b0d-122">Example</span></span>  
 <span data-ttu-id="02b0d-123">El siguiente XML muestra el uso del elemento \<> de serviceCertificate.</span><span class="sxs-lookup"><span data-stu-id="02b0d-123">The following XML shows the use of the \<serviceCertificate> element.</span></span> <span data-ttu-id="02b0d-124">El XML se toma `CustomToken` del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="02b0d-124">The XML is taken from the `CustomToken` sample.</span></span>  
  
```xml  
<serviceCertificate>  
  <certificateReference x509FindType="FindBySubjectName" findValue="localhost" storeLocation="LocalMachine" storeName="My"/>  
</serviceCertificate>  
```
