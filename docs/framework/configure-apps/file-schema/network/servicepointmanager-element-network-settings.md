---
title: Elemento <servicePointManager> (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#servicePointManager
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/servicePointManager
helpviewer_keywords:
- servicePointManager element
- <servicePointManager> element
ms.assetid: 6e5def51-3646-4ef6-a7bd-c69151321bec
ms.openlocfilehash: b7333016fea2d46285d3c98181c0ca4904c376f8
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089126"
---
# <a name="servicepointmanager-element-network-settings"></a><span data-ttu-id="e4d78-102">\<servicePointManager (elemento >) (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="e4d78-102">\<servicePointManager> Element (Network Settings)</span></span>
<span data-ttu-id="e4d78-103">Configura las conexiones a los recursos de red.</span><span class="sxs-lookup"><span data-stu-id="e4d78-103">Configures connections to network resources.</span></span>  

<span data-ttu-id="e4d78-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e4d78-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e4d78-105">&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="e4d78-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="e4d78-106">&nbsp;&nbsp;[ \**&nbsp;&nbsp;\<\** ](settings-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="e4d78-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\</span></span>
<span data-ttu-id="e4d78-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<servicePointManager >**</span><span class="sxs-lookup"><span data-stu-id="e4d78-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<servicePointManager>**</span></span>

## <a name="syntax"></a><span data-ttu-id="e4d78-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e4d78-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e4d78-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e4d78-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e4d78-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e4d78-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e4d78-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="e4d78-111">Attributes</span></span>  
  
|<span data-ttu-id="e4d78-112">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="e4d78-112">**Attribute**</span></span>|<span data-ttu-id="e4d78-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="e4d78-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`checkCertificateName`|<span data-ttu-id="e4d78-114">Especifica si el sistema debe comprobar que el nombre del certificado coincide con el nombre de host del servidor antes de usar el certificado.</span><span class="sxs-lookup"><span data-stu-id="e4d78-114">Specifies whether the system should verify that the name on the certificate matches the server host name before using the certificate.</span></span> <span data-ttu-id="e4d78-115">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="e4d78-115">The default value is `true`.</span></span>|  
|`checkCertificateRevocationList`|<span data-ttu-id="e4d78-116">Especifica si el sistema debe comprobar si el certificado se ha revocado antes de utilizar el certificado.</span><span class="sxs-lookup"><span data-stu-id="e4d78-116">Specifies whether the system should check whether the certificate has been revoked before using the certificate.</span></span> <span data-ttu-id="e4d78-117">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="e4d78-117">The default value is `false`.</span></span>|  
|`dnsRefreshTimeout`|<span data-ttu-id="e4d78-118">Especifica cuánto tiempo se almacenan en caché las resoluciones del servicio de nombres de dominio (DNS) junto con la opción Round Robin de DNS, en milisegundos.</span><span class="sxs-lookup"><span data-stu-id="e4d78-118">Specifies how long Domain Name Service (DNS) resolutions are cached in conjunction with the DNS Round Robin option, in milliseconds.</span></span> <span data-ttu-id="e4d78-119">El valor predeterminado es 120.000 milisegundos (dos minutos).</span><span class="sxs-lookup"><span data-stu-id="e4d78-119">The default value is 120,000 milliseconds (two minutes).</span></span>|  
|`enableDnsRoundRobin`|<span data-ttu-id="e4d78-120">Especifica si las resoluciones DNS de los nombres de host con varias direcciones IP (Protocolo de Internet) devuelven todas las direcciones, o solo la primera.</span><span class="sxs-lookup"><span data-stu-id="e4d78-120">Specifies whether DNS resolutions of host names with multiple Internet Protocol (IP) addresses return all the addresses, or just the first one.</span></span> <span data-ttu-id="e4d78-121">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="e4d78-121">The default value is `false`.</span></span>|  
|`encryptionPolicy`|<span data-ttu-id="e4d78-122">Especifica la Directiva de cifrado que se aplica a una sesión de SSL/TLS en una instancia de <xref:System.Net.ServicePointManager>.</span><span class="sxs-lookup"><span data-stu-id="e4d78-122">Specifies the encryption policy applied to an SSL/TLS session on a <xref:System.Net.ServicePointManager> instance.</span></span> <span data-ttu-id="e4d78-123">Los valores posibles son equivalentes a los valores de la enumeración <xref:System.Net.Security.EncryptionPolicy>.</span><span class="sxs-lookup"><span data-stu-id="e4d78-123">The possible values are equivalent to the values for the <xref:System.Net.Security.EncryptionPolicy> enumeration.</span></span> <span data-ttu-id="e4d78-124">El uso de <xref:System.Security.Authentication.CipherAlgorithmType.Null> es necesario cuando la Directiva de cifrado se establece en `NoEncryption`.</span><span class="sxs-lookup"><span data-stu-id="e4d78-124">The use of <xref:System.Security.Authentication.CipherAlgorithmType.Null> is required when the encryption policy is set to `NoEncryption`.</span></span> <span data-ttu-id="e4d78-125">El valor predeterminado es `RequireEncryption`.</span><span class="sxs-lookup"><span data-stu-id="e4d78-125">The default value is `RequireEncryption`.</span></span>|  
|`expect100Continue`|<span data-ttu-id="e4d78-126">Especifica si los métodos POST deben esperar recibir una respuesta `100-continue` del servidor.</span><span class="sxs-lookup"><span data-stu-id="e4d78-126">Specifies whether POST methods should expect to receive a `100-continue` response from the server.</span></span> <span data-ttu-id="e4d78-127">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="e4d78-127">The default value is `true`.</span></span>|  
|`useNagleAlgorithm`|<span data-ttu-id="e4d78-128">Especifica si las conexiones controladas por el administrador de puntos de servicio usan el algoritmo de Nagle.</span><span class="sxs-lookup"><span data-stu-id="e4d78-128">Specifies whether connections controlled by the service point manager use the Nagle algorithm.</span></span> <span data-ttu-id="e4d78-129">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="e4d78-129">The default value is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e4d78-130">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e4d78-130">Child Elements</span></span>  
 <span data-ttu-id="e4d78-131">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e4d78-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e4d78-132">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e4d78-132">Parent Elements</span></span>  
  
|<span data-ttu-id="e4d78-133">**Element**</span><span class="sxs-lookup"><span data-stu-id="e4d78-133">**Element**</span></span>|<span data-ttu-id="e4d78-134">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="e4d78-134">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="e4d78-135">Configuración</span><span class="sxs-lookup"><span data-stu-id="e4d78-135">Settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="e4d78-136">Configura opciones de red básicas para el espacio de nombres <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="e4d78-136">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e4d78-137">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e4d78-137">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="e4d78-138">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="e4d78-138">Configuration Files</span></span>  
 <span data-ttu-id="e4d78-139">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="e4d78-139">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4d78-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="e4d78-140">See also</span></span>

- <xref:System.Net.ServicePointManager>
- <xref:System.Net.Security.EncryptionPolicy>
- [<span data-ttu-id="e4d78-141">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="e4d78-141">Network Settings Schema</span></span>](index.md)
