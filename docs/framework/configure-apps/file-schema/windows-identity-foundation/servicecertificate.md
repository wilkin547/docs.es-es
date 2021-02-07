---
description: 'Más información acerca de: <serviceCertificate>'
title: <serviceCertificate>
ms.date: 03/30/2017
ms.assetid: 42c7f291-2ec3-43c5-8872-35897ff3c660
author: BrucePerlerMS
ms.openlocfilehash: d9940fd96667211b1f9fd672b824af84e0d5143a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99725329"
---
# \<serviceCertificate>

<span data-ttu-id="fdb3c-102">Configura el certificado X. 509 que se usa para cifrar y descifrar los tokens.</span><span class="sxs-lookup"><span data-stu-id="fdb3c-102">Configures the X.509 certificate that is used to encrypt and decrypt tokens.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceCertificate>**  
  
## <a name="syntax"></a><span data-ttu-id="fdb3c-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fdb3c-103">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fdb3c-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="fdb3c-104">Attributes and Elements</span></span>  

 <span data-ttu-id="fdb3c-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="fdb3c-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fdb3c-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="fdb3c-106">Attributes</span></span>  

 <span data-ttu-id="fdb3c-107">None</span><span class="sxs-lookup"><span data-stu-id="fdb3c-107">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="fdb3c-108">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="fdb3c-108">Child Elements</span></span>  
  
|<span data-ttu-id="fdb3c-109">Elemento</span><span class="sxs-lookup"><span data-stu-id="fdb3c-109">Element</span></span>|<span data-ttu-id="fdb3c-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="fdb3c-110">Description</span></span>|  
|-------------|-----------------|  
|[\<certificateReference>](certificatereference.md)|<span data-ttu-id="fdb3c-111">Especifica los valores que se usan para buscar y validar un certificado X. 509 en un almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="fdb3c-111">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fdb3c-112">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="fdb3c-112">Parent Elements</span></span>  
  
|<span data-ttu-id="fdb3c-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="fdb3c-113">Element</span></span>|<span data-ttu-id="fdb3c-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="fdb3c-114">Description</span></span>|  
|-------------|-----------------|  
|[\<federationConfiguration>](federationconfiguration.md)|<span data-ttu-id="fdb3c-115">Contiene la configuración que configura el <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) y el <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span><span class="sxs-lookup"><span data-stu-id="fdb3c-115">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="fdb3c-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fdb3c-116">Example</span></span>  

 <span data-ttu-id="fdb3c-117">El siguiente XML muestra el uso del \<serviceCertificate> elemento.</span><span class="sxs-lookup"><span data-stu-id="fdb3c-117">The following XML shows the use of the \<serviceCertificate> element.</span></span> <span data-ttu-id="fdb3c-118">El XML se toma del `CustomToken` ejemplo.</span><span class="sxs-lookup"><span data-stu-id="fdb3c-118">The XML is taken from the `CustomToken` sample.</span></span>  
  
```xml  
<serviceCertificate>  
  <certificateReference x509FindType="FindBySubjectName" findValue="localhost" storeLocation="LocalMachine" storeName="My"/>  
</serviceCertificate>  
```
