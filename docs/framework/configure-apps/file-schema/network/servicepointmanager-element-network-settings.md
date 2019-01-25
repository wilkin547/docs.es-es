---
title: '&lt;servicePointManager&gt; elemento (configuración de red)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#servicePointManager
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/servicePointManager
helpviewer_keywords:
- servicePointManager element
- <servicePointManager> element
ms.assetid: 6e5def51-3646-4ef6-a7bd-c69151321bec
ms.openlocfilehash: e30d38e3b925283b6048730aef2acc865be755b6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54651622"
---
# <a name="ltservicepointmanagergt-element-network-settings"></a><span data-ttu-id="63bf4-102">&lt;servicePointManager&gt; elemento (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="63bf4-102">&lt;servicePointManager&gt; Element (Network Settings)</span></span>
<span data-ttu-id="63bf4-103">Configura las conexiones a los recursos de red.</span><span class="sxs-lookup"><span data-stu-id="63bf4-103">Configures connections to network resources.</span></span>  
  
 <span data-ttu-id="63bf4-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="63bf4-104">\<configuration></span></span>  
<span data-ttu-id="63bf4-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="63bf4-105">\<system.net></span></span>  
<span data-ttu-id="63bf4-106">\<settings></span><span class="sxs-lookup"><span data-stu-id="63bf4-106">\<settings></span></span>  
<span data-ttu-id="63bf4-107">\<servicePointManager></span><span class="sxs-lookup"><span data-stu-id="63bf4-107">\<servicePointManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63bf4-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="63bf4-108">Syntax</span></span>  
  
```xml  
<servicePointManager  
  checkCertificateName="true|false"  
  checkCertificateRevocationList="true|false"  
  encryptionPolicy="AllowNoEncryption|NoEncryption|RequireEncryption"  
  expect100Continue="true|false"  
  useNagleAlgorithm="true|false"  
  enableDnsRoundRobin="true|false"  
  dnsRefreshTimeout="time"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="63bf4-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="63bf4-109">Attributes and Elements</span></span>  
 <span data-ttu-id="63bf4-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="63bf4-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="63bf4-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="63bf4-111">Attributes</span></span>  
  
|<span data-ttu-id="63bf4-112">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="63bf4-112">**Attribute**</span></span>|<span data-ttu-id="63bf4-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="63bf4-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`checkCertificateName`|<span data-ttu-id="63bf4-114">Especifica si el sistema debe comprobar que el nombre del certificado coincide con el nombre de host del servidor antes de usar el certificado.</span><span class="sxs-lookup"><span data-stu-id="63bf4-114">Specifies whether the system should verify that the name on the certificate matches the server host name before using the certificate.</span></span> <span data-ttu-id="63bf4-115">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="63bf4-115">The default value is `true`.</span></span>|  
|`checkCertificateRevocationList`|<span data-ttu-id="63bf4-116">Especifica si el sistema debe comprobar si se ha revocado el certificado antes de usar el certificado.</span><span class="sxs-lookup"><span data-stu-id="63bf4-116">Specifies whether the system should check whether the certificate has been revoked before using the certificate.</span></span> <span data-ttu-id="63bf4-117">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="63bf4-117">The default value is `false`.</span></span>|  
|`dnsRefreshTimeout`|<span data-ttu-id="63bf4-118">Especifica cuánto nombre servicio dominio (DNS) se almacenan en caché las resoluciones junto con la opción de operación por turnos DNS, en milisegundos.</span><span class="sxs-lookup"><span data-stu-id="63bf4-118">Specifies how long Domain Name Service (DNS) resolutions are cached in conjunction with the DNS Round Robin option, in milliseconds.</span></span> <span data-ttu-id="63bf4-119">El valor predeterminado es 120.000 milisegundos (dos minutos).</span><span class="sxs-lookup"><span data-stu-id="63bf4-119">The default value is 120,000 milliseconds (two minutes).</span></span>|  
|`enableDnsRoundRobin`|<span data-ttu-id="63bf4-120">Especifica si las resoluciones DNS del host de nombres con varias direcciones de protocolo de Internet (IP) devueltas todas las direcciones o solo la primera de ellas.</span><span class="sxs-lookup"><span data-stu-id="63bf4-120">Specifies whether DNS resolutions of host names with multiple Internet Protocol (IP) addresses return all the addresses, or just the first one.</span></span> <span data-ttu-id="63bf4-121">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="63bf4-121">The default value is `false`.</span></span>|  
|`encryptionPolicy`|<span data-ttu-id="63bf4-122">Especifica la directiva de cifrado que se aplica a una sesión SSL/TLS en un <xref:System.Net.ServicePointManager> instancia.</span><span class="sxs-lookup"><span data-stu-id="63bf4-122">Specifies the encryption policy applied to an SSL/TLS session on a <xref:System.Net.ServicePointManager> instance.</span></span> <span data-ttu-id="63bf4-123">Los valores posibles son equivalentes a los valores de la <xref:System.Net.Security.EncryptionPolicy> enumeración.</span><span class="sxs-lookup"><span data-stu-id="63bf4-123">The possible values are equivalent to the values for the <xref:System.Net.Security.EncryptionPolicy> enumeration.</span></span> <span data-ttu-id="63bf4-124">El uso de <xref:System.Security.Authentication.CipherAlgorithmType.Null> es necesaria cuando la directiva de cifrado se establece en `NoEncryption`.</span><span class="sxs-lookup"><span data-stu-id="63bf4-124">The use of <xref:System.Security.Authentication.CipherAlgorithmType.Null> is required when the encryption policy is set to `NoEncryption`.</span></span> <span data-ttu-id="63bf4-125">El valor predeterminado es `RequireEncryption`.</span><span class="sxs-lookup"><span data-stu-id="63bf4-125">The default value is `RequireEncryption`.</span></span>|  
|`expect100Continue`|<span data-ttu-id="63bf4-126">Especifica si los métodos POST deben esperar recibir una `100-continue` respuesta del servidor.</span><span class="sxs-lookup"><span data-stu-id="63bf4-126">Specifies whether POST methods should expect to receive a `100-continue` response from the server.</span></span> <span data-ttu-id="63bf4-127">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="63bf4-127">The default value is `true`.</span></span>|  
|`useNagleAlgorithm`|<span data-ttu-id="63bf4-128">Especifica si las conexiones controladas por el Administrador de punto de servicio utilizan el algoritmo de Nagle.</span><span class="sxs-lookup"><span data-stu-id="63bf4-128">Specifies whether connections controlled by the service point manager use the Nagle algorithm.</span></span> <span data-ttu-id="63bf4-129">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="63bf4-129">The default value is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="63bf4-130">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="63bf4-130">Child Elements</span></span>  
 <span data-ttu-id="63bf4-131">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="63bf4-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="63bf4-132">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="63bf4-132">Parent Elements</span></span>  
  
|<span data-ttu-id="63bf4-133">**Element**</span><span class="sxs-lookup"><span data-stu-id="63bf4-133">**Element**</span></span>|<span data-ttu-id="63bf4-134">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="63bf4-134">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="63bf4-135">Configuración</span><span class="sxs-lookup"><span data-stu-id="63bf4-135">Settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="63bf4-136">Configura opciones de red básicas para el espacio de nombres <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="63bf4-136">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="63bf4-137">Comentarios</span><span class="sxs-lookup"><span data-stu-id="63bf4-137">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="63bf4-138">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="63bf4-138">Configuration Files</span></span>  
 <span data-ttu-id="63bf4-139">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="63bf4-139">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63bf4-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="63bf4-140">See also</span></span>
- <xref:System.Net.ServicePointManager>
- <xref:System.Net.Security.EncryptionPolicy>
- [<span data-ttu-id="63bf4-141">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="63bf4-141">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
