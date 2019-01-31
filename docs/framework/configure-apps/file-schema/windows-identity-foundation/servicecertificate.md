---
title: <serviceCertificate>
ms.date: 03/30/2017
ms.assetid: 42c7f291-2ec3-43c5-8872-35897ff3c660
author: BrucePerlerMS
ms.openlocfilehash: 328d074f9edc5ddf871308a7e3d694bf94adea78
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55261614"
---
# <a name="servicecertificate"></a><span data-ttu-id="c9ff4-101">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="c9ff4-101">\<serviceCertificate></span></span>
<span data-ttu-id="c9ff4-102">Configura el certificado X.509 que se usa para cifrar y descifrar los tokens.</span><span class="sxs-lookup"><span data-stu-id="c9ff4-102">Configures the X.509 certificate that is used to encrypt and decrypt tokens.</span></span>  
  
 <span data-ttu-id="c9ff4-103">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="c9ff4-103">\<system.identityModel.services></span></span>  
<span data-ttu-id="c9ff4-104">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="c9ff4-104">\<federationConfiguration></span></span>  
<span data-ttu-id="c9ff4-105">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="c9ff4-105">\<serviceCertificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9ff4-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c9ff4-106">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c9ff4-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c9ff4-107">Attributes and Elements</span></span>  
 <span data-ttu-id="c9ff4-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c9ff4-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c9ff4-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="c9ff4-109">Attributes</span></span>  
 <span data-ttu-id="c9ff4-110">Ninguna</span><span class="sxs-lookup"><span data-stu-id="c9ff4-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c9ff4-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c9ff4-111">Child Elements</span></span>  
  
|<span data-ttu-id="c9ff4-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="c9ff4-112">Element</span></span>|<span data-ttu-id="c9ff4-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="c9ff4-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c9ff4-114">\<certificateReference></span><span class="sxs-lookup"><span data-stu-id="c9ff4-114">\<certificateReference></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatereference.md)|<span data-ttu-id="c9ff4-115">Especifica la configuración que se usa para buscar y validar un certificado X.509 en un almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="c9ff4-115">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c9ff4-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c9ff4-116">Parent Elements</span></span>  
  
|<span data-ttu-id="c9ff4-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="c9ff4-117">Element</span></span>|<span data-ttu-id="c9ff4-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="c9ff4-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c9ff4-119">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="c9ff4-119">\<federationConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|<span data-ttu-id="c9ff4-120">Contiene la configuración que establece el <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) y la <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span><span class="sxs-lookup"><span data-stu-id="c9ff4-120">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c9ff4-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c9ff4-121">Example</span></span>  
 <span data-ttu-id="c9ff4-122">El siguiente XML muestra el uso de la \<serviceCertificate > elemento.</span><span class="sxs-lookup"><span data-stu-id="c9ff4-122">The following XML shows the use of the \<serviceCertificate> element.</span></span> <span data-ttu-id="c9ff4-123">El XML procede de la `CustomToken` ejemplo.</span><span class="sxs-lookup"><span data-stu-id="c9ff4-123">The XML is taken from the `CustomToken` sample.</span></span>  
  
```xml  
<serviceCertificate>  
  <certificateReference x509FindType="FindBySubjectName" findValue="localhost" storeLocation="LocalMachine" storeName="My"/>  
</serviceCertificate>  
```
