---
title: <serviceCertificate>
ms.date: 03/30/2017
ms.assetid: 42c7f291-2ec3-43c5-8872-35897ff3c660
author: BrucePerlerMS
ms.openlocfilehash: ce8be6eea5469b099a368a0b62e791faa7e3cbfc
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91156997"
---
# \<serviceCertificate>

<span data-ttu-id="c1189-101">Configura el certificado X. 509 que se usa para cifrar y descifrar los tokens.</span><span class="sxs-lookup"><span data-stu-id="c1189-101">Configures the X.509 certificate that is used to encrypt and decrypt tokens.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceCertificate>**  
  
## <a name="syntax"></a><span data-ttu-id="c1189-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c1189-102">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c1189-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c1189-103">Attributes and Elements</span></span>  

 <span data-ttu-id="c1189-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c1189-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c1189-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="c1189-105">Attributes</span></span>  

 <span data-ttu-id="c1189-106">None</span><span class="sxs-lookup"><span data-stu-id="c1189-106">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c1189-107">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c1189-107">Child Elements</span></span>  
  
|<span data-ttu-id="c1189-108">Elemento</span><span class="sxs-lookup"><span data-stu-id="c1189-108">Element</span></span>|<span data-ttu-id="c1189-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="c1189-109">Description</span></span>|  
|-------------|-----------------|  
|[\<certificateReference>](certificatereference.md)|<span data-ttu-id="c1189-110">Especifica los valores que se usan para buscar y validar un certificado X. 509 en un almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="c1189-110">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c1189-111">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c1189-111">Parent Elements</span></span>  
  
|<span data-ttu-id="c1189-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="c1189-112">Element</span></span>|<span data-ttu-id="c1189-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="c1189-113">Description</span></span>|  
|-------------|-----------------|  
|[\<federationConfiguration>](federationconfiguration.md)|<span data-ttu-id="c1189-114">Contiene la configuración que configura el <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) y el <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span><span class="sxs-lookup"><span data-stu-id="c1189-114">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c1189-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c1189-115">Example</span></span>  

 <span data-ttu-id="c1189-116">El siguiente XML muestra el uso del \<serviceCertificate> elemento.</span><span class="sxs-lookup"><span data-stu-id="c1189-116">The following XML shows the use of the \<serviceCertificate> element.</span></span> <span data-ttu-id="c1189-117">El XML se toma del `CustomToken` ejemplo.</span><span class="sxs-lookup"><span data-stu-id="c1189-117">The XML is taken from the `CustomToken` sample.</span></span>  
  
```xml  
<serviceCertificate>  
  <certificateReference x509FindType="FindBySubjectName" findValue="localhost" storeLocation="LocalMachine" storeName="My"/>  
</serviceCertificate>  
```
