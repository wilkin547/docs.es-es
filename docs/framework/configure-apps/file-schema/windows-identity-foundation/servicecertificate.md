---
title: '&lt;ServiceCertificate&gt;'
ms.date: 03/30/2017
ms.assetid: 42c7f291-2ec3-43c5-8872-35897ff3c660
author: BrucePerlerMS
ms.openlocfilehash: 008d2269a72759117658e27ec130cc8cf62cfdfa
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "47084311"
---
# <a name="ltservicecertificategt"></a><span data-ttu-id="c2225-102">&lt;ServiceCertificate&gt;</span><span class="sxs-lookup"><span data-stu-id="c2225-102">&lt;serviceCertificate&gt;</span></span>
<span data-ttu-id="c2225-103">Configura el certificado X.509 que se usa para cifrar y descifrar los tokens.</span><span class="sxs-lookup"><span data-stu-id="c2225-103">Configures the X.509 certificate that is used to encrypt and decrypt tokens.</span></span>  
  
 <span data-ttu-id="c2225-104">\<system.identityModel.services ></span><span class="sxs-lookup"><span data-stu-id="c2225-104">\<system.identityModel.services></span></span>  
<span data-ttu-id="c2225-105">\<federationConfiguration ></span><span class="sxs-lookup"><span data-stu-id="c2225-105">\<federationConfiguration></span></span>  
<span data-ttu-id="c2225-106">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="c2225-106">\<serviceCertificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2225-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c2225-107">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c2225-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c2225-108">Attributes and Elements</span></span>  
 <span data-ttu-id="c2225-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c2225-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c2225-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="c2225-110">Attributes</span></span>  
 <span data-ttu-id="c2225-111">Ninguna</span><span class="sxs-lookup"><span data-stu-id="c2225-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c2225-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c2225-112">Child Elements</span></span>  
  
|<span data-ttu-id="c2225-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="c2225-113">Element</span></span>|<span data-ttu-id="c2225-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="c2225-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c2225-115">\<certificateReference ></span><span class="sxs-lookup"><span data-stu-id="c2225-115">\<certificateReference></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatereference.md)|<span data-ttu-id="c2225-116">Especifica la configuración que se usa para buscar y validar un certificado X.509 en un almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="c2225-116">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c2225-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c2225-117">Parent Elements</span></span>  
  
|<span data-ttu-id="c2225-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="c2225-118">Element</span></span>|<span data-ttu-id="c2225-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="c2225-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c2225-120">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="c2225-120">\<federationConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|<span data-ttu-id="c2225-121">Contiene la configuración que establece el <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) y la <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span><span class="sxs-lookup"><span data-stu-id="c2225-121">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c2225-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c2225-122">Example</span></span>  
 <span data-ttu-id="c2225-123">El siguiente XML muestra el uso de la \<serviceCertificate > elemento.</span><span class="sxs-lookup"><span data-stu-id="c2225-123">The following XML shows the use of the \<serviceCertificate> element.</span></span> <span data-ttu-id="c2225-124">El XML procede de la `CustomToken` ejemplo.</span><span class="sxs-lookup"><span data-stu-id="c2225-124">The XML is taken from the `CustomToken` sample.</span></span>  
  
```xml  
<serviceCertificate>  
  <certificateReference x509FindType="FindBySubjectName" findValue="localhost" storeLocation="LocalMachine" storeName="My"/>  
</serviceCertificate>  
```
