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
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 2aaf590975d9fd3f5d78cb64d8d2b1c38c0e8dc7
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2018
ms.locfileid: "48033511"
---
# <a name="ltservicepointmanagergt-element-network-settings"></a><span data-ttu-id="d5830-102">&lt;servicePointManager&gt; elemento (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="d5830-102">&lt;servicePointManager&gt; Element (Network Settings)</span></span>
<span data-ttu-id="d5830-103">Configura las conexiones a los recursos de red.</span><span class="sxs-lookup"><span data-stu-id="d5830-103">Configures connections to network resources.</span></span>  
  
 <span data-ttu-id="d5830-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="d5830-104">\<configuration></span></span>  
<span data-ttu-id="d5830-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="d5830-105">\<system.net></span></span>  
<span data-ttu-id="d5830-106">\<Configuración ></span><span class="sxs-lookup"><span data-stu-id="d5830-106">\<settings></span></span>  
<span data-ttu-id="d5830-107">\<servicePointManager ></span><span class="sxs-lookup"><span data-stu-id="d5830-107">\<servicePointManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5830-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d5830-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d5830-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d5830-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d5830-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d5830-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d5830-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="d5830-111">Attributes</span></span>  
  
|<span data-ttu-id="d5830-112">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="d5830-112">**Attribute**</span></span>|<span data-ttu-id="d5830-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="d5830-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`checkCertificateName`|<span data-ttu-id="d5830-114">Especifica si el sistema debe comprobar que el nombre del certificado coincide con el nombre de host del servidor antes de usar el certificado.</span><span class="sxs-lookup"><span data-stu-id="d5830-114">Specifies whether the system should verify that the name on the certificate matches the server host name before using the certificate.</span></span> <span data-ttu-id="d5830-115">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="d5830-115">The default value is `true`.</span></span>|  
|`checkCertificateRevocationList`|<span data-ttu-id="d5830-116">Especifica si el sistema debe comprobar si se ha revocado el certificado antes de usar el certificado.</span><span class="sxs-lookup"><span data-stu-id="d5830-116">Specifies whether the system should check whether the certificate has been revoked before using the certificate.</span></span> <span data-ttu-id="d5830-117">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="d5830-117">The default value is `false`.</span></span>|  
|`dnsRefreshTimeout`|<span data-ttu-id="d5830-118">Especifica cuánto nombre servicio dominio (DNS) se almacenan en caché las resoluciones junto con la opción de operación por turnos DNS, en milisegundos.</span><span class="sxs-lookup"><span data-stu-id="d5830-118">Specifies how long Domain Name Service (DNS) resolutions are cached in conjunction with the DNS Round Robin option, in milliseconds.</span></span> <span data-ttu-id="d5830-119">El valor predeterminado es 120.000 milisegundos (dos minutos).</span><span class="sxs-lookup"><span data-stu-id="d5830-119">The default value is 120,000 milliseconds (two minutes).</span></span>|  
|`enableDnsRoundRobin`|<span data-ttu-id="d5830-120">Especifica si las resoluciones DNS del host de nombres con varias direcciones de protocolo de Internet (IP) devueltas todas las direcciones o solo la primera de ellas.</span><span class="sxs-lookup"><span data-stu-id="d5830-120">Specifies whether DNS resolutions of host names with multiple Internet Protocol (IP) addresses return all the addresses, or just the first one.</span></span> <span data-ttu-id="d5830-121">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="d5830-121">The default value is `false`.</span></span>|  
|`encryptionPolicy`|<span data-ttu-id="d5830-122">Especifica la directiva de cifrado que se aplica a una sesión SSL/TLS en un <xref:System.Net.ServicePointManager> instancia.</span><span class="sxs-lookup"><span data-stu-id="d5830-122">Specifies the encryption policy applied to an SSL/TLS session on a <xref:System.Net.ServicePointManager> instance.</span></span> <span data-ttu-id="d5830-123">Los valores posibles son equivalentes a los valores de la <xref:System.Net.Security.EncryptionPolicy> enumeración.</span><span class="sxs-lookup"><span data-stu-id="d5830-123">The possible values are equivalent to the values for the <xref:System.Net.Security.EncryptionPolicy> enumeration.</span></span> <span data-ttu-id="d5830-124">El uso de <xref:System.Security.Authentication.CipherAlgorithmType.Null> es necesaria cuando la directiva de cifrado se establece en `NoEncryption`.</span><span class="sxs-lookup"><span data-stu-id="d5830-124">The use of <xref:System.Security.Authentication.CipherAlgorithmType.Null> is required when the encryption policy is set to `NoEncryption`.</span></span> <span data-ttu-id="d5830-125">El valor predeterminado es `RequireEncryption`.</span><span class="sxs-lookup"><span data-stu-id="d5830-125">The default value is `RequireEncryption`.</span></span>|  
|`expect100Continue`|<span data-ttu-id="d5830-126">Especifica si los métodos POST deben esperar recibir una `100-continue` respuesta del servidor.</span><span class="sxs-lookup"><span data-stu-id="d5830-126">Specifies whether POST methods should expect to receive a `100-continue` response from the server.</span></span> <span data-ttu-id="d5830-127">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="d5830-127">The default value is `true`.</span></span>|  
|`useNagleAlgorithm`|<span data-ttu-id="d5830-128">Especifica si las conexiones controladas por el Administrador de punto de servicio utilizan el algoritmo de Nagle.</span><span class="sxs-lookup"><span data-stu-id="d5830-128">Specifies whether connections controlled by the service point manager use the Nagle algorithm.</span></span> <span data-ttu-id="d5830-129">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="d5830-129">The default value is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d5830-130">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d5830-130">Child Elements</span></span>  
 <span data-ttu-id="d5830-131">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="d5830-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d5830-132">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d5830-132">Parent Elements</span></span>  
  
|<span data-ttu-id="d5830-133">**Element**</span><span class="sxs-lookup"><span data-stu-id="d5830-133">**Element**</span></span>|<span data-ttu-id="d5830-134">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="d5830-134">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="d5830-135">Configuración</span><span class="sxs-lookup"><span data-stu-id="d5830-135">Settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="d5830-136">Configura opciones de red básicas para el espacio de nombres <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="d5830-136">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d5830-137">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d5830-137">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="d5830-138">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="d5830-138">Configuration Files</span></span>  
 <span data-ttu-id="d5830-139">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="d5830-139">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5830-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="d5830-140">See Also</span></span>  
 <xref:System.Net.ServicePointManager>  
 <xref:System.Net.Security.EncryptionPolicy>  
 [<span data-ttu-id="d5830-141">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="d5830-141">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
