---
title: <serviceCertificate>
ms.date: 03/30/2017
ms.assetid: 42c7f291-2ec3-43c5-8872-35897ff3c660
author: BrucePerlerMS
ms.openlocfilehash: a3aba5618855f7225dc8a427516eaa72b45f6e8b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942410"
---
# <a name="servicecertificate"></a><span data-ttu-id="a7a6f-101">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="a7a6f-101">\<serviceCertificate></span></span>
<span data-ttu-id="a7a6f-102">Configura el certificado X. 509 que se usa para cifrar y descifrar los tokens.</span><span class="sxs-lookup"><span data-stu-id="a7a6f-102">Configures the X.509 certificate that is used to encrypt and decrypt tokens.</span></span>  
  
 <span data-ttu-id="a7a6f-103">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="a7a6f-103">\<system.identityModel.services></span></span>  
<span data-ttu-id="a7a6f-104">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="a7a6f-104">\<federationConfiguration></span></span>  
<span data-ttu-id="a7a6f-105">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="a7a6f-105">\<serviceCertificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7a6f-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a7a6f-106">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a7a6f-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a7a6f-107">Attributes and Elements</span></span>  
 <span data-ttu-id="a7a6f-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a7a6f-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a7a6f-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="a7a6f-109">Attributes</span></span>  
 <span data-ttu-id="a7a6f-110">None</span><span class="sxs-lookup"><span data-stu-id="a7a6f-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a7a6f-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a7a6f-111">Child Elements</span></span>  
  
|<span data-ttu-id="a7a6f-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="a7a6f-112">Element</span></span>|<span data-ttu-id="a7a6f-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="a7a6f-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a7a6f-114">\<certificateReference></span><span class="sxs-lookup"><span data-stu-id="a7a6f-114">\<certificateReference></span></span>](certificatereference.md)|<span data-ttu-id="a7a6f-115">Especifica los valores que se usan para buscar y validar un certificado X. 509 en un almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="a7a6f-115">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a7a6f-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a7a6f-116">Parent Elements</span></span>  
  
|<span data-ttu-id="a7a6f-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="a7a6f-117">Element</span></span>|<span data-ttu-id="a7a6f-118">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="a7a6f-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a7a6f-119">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="a7a6f-119">\<federationConfiguration></span></span>](federationconfiguration.md)|<span data-ttu-id="a7a6f-120">Contiene la configuración que configura el <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) y el <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span><span class="sxs-lookup"><span data-stu-id="a7a6f-120">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a7a6f-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a7a6f-121">Example</span></span>  
 <span data-ttu-id="a7a6f-122">El siguiente XML muestra el uso del elemento \<> de serviceCertificate.</span><span class="sxs-lookup"><span data-stu-id="a7a6f-122">The following XML shows the use of the \<serviceCertificate> element.</span></span> <span data-ttu-id="a7a6f-123">El XML se toma `CustomToken` del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a7a6f-123">The XML is taken from the `CustomToken` sample.</span></span>  
  
```xml  
<serviceCertificate>  
  <certificateReference x509FindType="FindBySubjectName" findValue="localhost" storeLocation="LocalMachine" storeName="My"/>  
</serviceCertificate>  
```
