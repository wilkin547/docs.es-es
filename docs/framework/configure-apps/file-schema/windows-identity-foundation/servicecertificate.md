---
title: '&lt;serviceCertificate&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 42c7f291-2ec3-43c5-8872-35897ff3c660
caps.latest.revision: "5"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 1373d1e95a0e569f5e5cf433d305d008b4daf838
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltservicecertificategt"></a><span data-ttu-id="00e45-102">&lt;serviceCertificate&gt;</span><span class="sxs-lookup"><span data-stu-id="00e45-102">&lt;serviceCertificate&gt;</span></span>
<span data-ttu-id="00e45-103">Configura el certificado X.509 que se utiliza para cifrar y descifrar los tokens.</span><span class="sxs-lookup"><span data-stu-id="00e45-103">Configures the X.509 certificate that is used to encrypt and decrypt tokens.</span></span>  
  
 <span data-ttu-id="00e45-104">\<system.identityModel.services ></span><span class="sxs-lookup"><span data-stu-id="00e45-104">\<system.identityModel.services></span></span>  
<span data-ttu-id="00e45-105">\<federationConfiguration ></span><span class="sxs-lookup"><span data-stu-id="00e45-105">\<federationConfiguration></span></span>  
<span data-ttu-id="00e45-106">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="00e45-106">\<serviceCertificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00e45-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="00e45-107">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="00e45-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="00e45-108">Attributes and Elements</span></span>  
 <span data-ttu-id="00e45-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="00e45-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="00e45-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="00e45-110">Attributes</span></span>  
 <span data-ttu-id="00e45-111">Ninguna</span><span class="sxs-lookup"><span data-stu-id="00e45-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="00e45-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="00e45-112">Child Elements</span></span>  
  
|<span data-ttu-id="00e45-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="00e45-113">Element</span></span>|<span data-ttu-id="00e45-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="00e45-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="00e45-115">\<certificateReference ></span><span class="sxs-lookup"><span data-stu-id="00e45-115">\<certificateReference></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatereference.md)|<span data-ttu-id="00e45-116">Especifica valores que se usan para encontrar y validar un certificado X.509 en un almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="00e45-116">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="00e45-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="00e45-117">Parent Elements</span></span>  
  
|<span data-ttu-id="00e45-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="00e45-118">Element</span></span>|<span data-ttu-id="00e45-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="00e45-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="00e45-120">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="00e45-120">\<federationConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|<span data-ttu-id="00e45-121">Contiene los valores que configuran la <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) y <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span><span class="sxs-lookup"><span data-stu-id="00e45-121">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="00e45-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="00e45-122">Example</span></span>  
 <span data-ttu-id="00e45-123">El siguiente XML muestra el uso de la \<serviceCertificate > elemento.</span><span class="sxs-lookup"><span data-stu-id="00e45-123">The following XML shows the use of the \<serviceCertificate> element.</span></span> <span data-ttu-id="00e45-124">El XML procede de la `CustomToken` ejemplo.</span><span class="sxs-lookup"><span data-stu-id="00e45-124">The XML is taken from the `CustomToken` sample.</span></span>  
  
```xml  
<serviceCertificate>  
  <certificateReference x509FindType="FindBySubjectName" findValue="localhost" storeLocation="LocalMachine" storeName="My"/>  
</serviceCertificate>  
```
