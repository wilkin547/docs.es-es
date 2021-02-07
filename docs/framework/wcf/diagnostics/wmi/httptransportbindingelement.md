---
description: 'Más información acerca de: HttpTransportBindingElement'
title: HttpTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 088a7bce-6bb2-4839-ad74-f68d4b1aa0f9
ms.openlocfilehash: 6c516dd7124d52828145787d55421d12031c2d36
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99757376"
---
# <a name="httptransportbindingelement"></a><span data-ttu-id="72f2d-103">HttpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="72f2d-103">HttpTransportBindingElement</span></span>

<span data-ttu-id="72f2d-104">HttpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="72f2d-104">HttpTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72f2d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="72f2d-105">Syntax</span></span>  
  
```csharp
class HttpTransportBindingElement : TransportBindingElement  
{  
  boolean AllowCookies;  
  string AuthenticationScheme;  
  boolean BypassProxyOnLocal;  
  string HostNameComparisonMode;  
  boolean KeepAliveEnabled;  
  sint32 MaxBufferSize;  
  string ProxyAddress;  
  string ProxyAuthenticationScheme;  
  string Realm;  
  string TransferMode;  
  boolean UnsafeConnectionNtlmAuthentication;  
  boolean UseDefaultWebProxy;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="72f2d-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="72f2d-106">Methods</span></span>  

 <span data-ttu-id="72f2d-107">La clase HttpTransportBindingElement no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="72f2d-107">The HttpTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="72f2d-108">Propiedades</span><span class="sxs-lookup"><span data-stu-id="72f2d-108">Properties</span></span>  

 <span data-ttu-id="72f2d-109">La clase HttpTransportBindingElement tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="72f2d-109">The HttpTransportBindingElement class has the following properties:</span></span>  
  
### <a name="allowcookies"></a><span data-ttu-id="72f2d-110">AllowCookies</span><span class="sxs-lookup"><span data-stu-id="72f2d-110">AllowCookies</span></span>  

 <span data-ttu-id="72f2d-111">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="72f2d-111">Data type: boolean</span></span>  
  
 <span data-ttu-id="72f2d-112">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="72f2d-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="72f2d-113">Un valor que indica si el cliente acepta las cookies y las propaga en solicitudes futuras.</span><span class="sxs-lookup"><span data-stu-id="72f2d-113">A value that indicates whether the client accepts cookies and propagates them on future requests.</span></span>  
  
### <a name="authenticationscheme"></a><span data-ttu-id="72f2d-114">AuthenticationScheme</span><span class="sxs-lookup"><span data-stu-id="72f2d-114">AuthenticationScheme</span></span>  

 <span data-ttu-id="72f2d-115">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="72f2d-115">Data type: string</span></span>  
  
 <span data-ttu-id="72f2d-116">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="72f2d-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="72f2d-117">El esquema de autenticación usado para autenticar las solicitudes del cliente que está procesando un agente de escucha HTTP.</span><span class="sxs-lookup"><span data-stu-id="72f2d-117">The authentication scheme used to authenticate client requests being processed by an HTTP listener.</span></span>  
  
### <a name="bypassproxyonlocal"></a><span data-ttu-id="72f2d-118">BypassProxyOnLocal</span><span class="sxs-lookup"><span data-stu-id="72f2d-118">BypassProxyOnLocal</span></span>  

 <span data-ttu-id="72f2d-119">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="72f2d-119">Data type: boolean</span></span>  
  
 <span data-ttu-id="72f2d-120">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="72f2d-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="72f2d-121">Un valor que indica si se omiten servidores proxy para direcciones locales.</span><span class="sxs-lookup"><span data-stu-id="72f2d-121">A value that indicates whether proxies are ignored for local addresses.</span></span>  
  
### <a name="hostnamecomparisonmode"></a><span data-ttu-id="72f2d-122">HostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="72f2d-122">HostNameComparisonMode</span></span>  

 <span data-ttu-id="72f2d-123">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="72f2d-123">Data type: string</span></span>  
  
 <span data-ttu-id="72f2d-124">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="72f2d-124">Access type: Read-only</span></span>  
  
 <span data-ttu-id="72f2d-125">Un valor que indica si el nombre del host se usa para alcanzar el servicio al coincidir con el URI.</span><span class="sxs-lookup"><span data-stu-id="72f2d-125">A value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>  
  
### <a name="keepaliveenabled"></a><span data-ttu-id="72f2d-126">KeepAliveEnabled</span><span class="sxs-lookup"><span data-stu-id="72f2d-126">KeepAliveEnabled</span></span>  

 <span data-ttu-id="72f2d-127">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="72f2d-127">Data type: boolean</span></span>  
  
 <span data-ttu-id="72f2d-128">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="72f2d-128">Access type: Read-only</span></span>  
  
 <span data-ttu-id="72f2d-129">Cuando se habilita, las conexiones HTTP se mantienen vivas sin tener en cuenta el nivel de actividad.</span><span class="sxs-lookup"><span data-stu-id="72f2d-129">When enabled, HTTP connections are kept alive regardless of activity level.</span></span>  
  
### <a name="maxbuffersize"></a><span data-ttu-id="72f2d-130">MaxBufferSize</span><span class="sxs-lookup"><span data-stu-id="72f2d-130">MaxBufferSize</span></span>  

 <span data-ttu-id="72f2d-131">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="72f2d-131">Data type: sint32</span></span>  
  
 <span data-ttu-id="72f2d-132">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="72f2d-132">Access type: Read-only</span></span>  
  
 <span data-ttu-id="72f2d-133">El tamaño máximo del grupo de búferes.</span><span class="sxs-lookup"><span data-stu-id="72f2d-133">The maximum size of the buffer pool.</span></span>  
  
### <a name="proxyaddress"></a><span data-ttu-id="72f2d-134">ProxyAddress</span><span class="sxs-lookup"><span data-stu-id="72f2d-134">ProxyAddress</span></span>  

 <span data-ttu-id="72f2d-135">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="72f2d-135">Data type: string</span></span>  
  
 <span data-ttu-id="72f2d-136">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="72f2d-136">Access type: Read-only</span></span>  
  
 <span data-ttu-id="72f2d-137">Un URI que contiene la dirección del proxy que utilizar para las solicitudes HTTP.</span><span class="sxs-lookup"><span data-stu-id="72f2d-137">A URI that contains the address of the proxy to use for HTTP requests.</span></span>  
  
### <a name="proxyauthenticationscheme"></a><span data-ttu-id="72f2d-138">ProxyAuthenticationScheme</span><span class="sxs-lookup"><span data-stu-id="72f2d-138">ProxyAuthenticationScheme</span></span>  

 <span data-ttu-id="72f2d-139">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="72f2d-139">Data type: string</span></span>  
  
 <span data-ttu-id="72f2d-140">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="72f2d-140">Access type: Read-only</span></span>  
  
 <span data-ttu-id="72f2d-141">El esquema de autenticación usado para autenticar las solicitudes del cliente que un proxy HTTP está procesando.</span><span class="sxs-lookup"><span data-stu-id="72f2d-141">The authentication scheme used to authenticate client requests being processed by an HTTP proxy.</span></span>  
  
### <a name="realm"></a><span data-ttu-id="72f2d-142">Dominio</span><span class="sxs-lookup"><span data-stu-id="72f2d-142">Realm</span></span>  

 <span data-ttu-id="72f2d-143">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="72f2d-143">Data type: string</span></span>  
  
 <span data-ttu-id="72f2d-144">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="72f2d-144">Access type: Read-only</span></span>  
  
 <span data-ttu-id="72f2d-145">El dominio kerberos de autenticación.</span><span class="sxs-lookup"><span data-stu-id="72f2d-145">The authentication realm.</span></span>  
  
### <a name="transfermode"></a><span data-ttu-id="72f2d-146">TransferMode</span><span class="sxs-lookup"><span data-stu-id="72f2d-146">TransferMode</span></span>  

 <span data-ttu-id="72f2d-147">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="72f2d-147">Data type: string</span></span>  
  
 <span data-ttu-id="72f2d-148">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="72f2d-148">Access type: Read-only</span></span>  
  
 <span data-ttu-id="72f2d-149">Un valor que especifica si los mensajes se almacenan en búfer, se transmiten o si son una solicitud o una respuesta.</span><span class="sxs-lookup"><span data-stu-id="72f2d-149">A value that specifies whether messages are buffered or streamed or a request or response.</span></span>  
  
### <a name="unsafeconnectionntlmauthentication"></a><span data-ttu-id="72f2d-150">UnsafeConnectionNtlmAuthentication</span><span class="sxs-lookup"><span data-stu-id="72f2d-150">UnsafeConnectionNtlmAuthentication</span></span>  

 <span data-ttu-id="72f2d-151">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="72f2d-151">Data type: boolean</span></span>  
  
 <span data-ttu-id="72f2d-152">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="72f2d-152">Access type: Read-only</span></span>  
  
 <span data-ttu-id="72f2d-153">Un valor que indica si la conexión compartida no segura está habilitada en el servidor.</span><span class="sxs-lookup"><span data-stu-id="72f2d-153">A value that indicates whether Unsafe Connection Sharing is enabled on the server.</span></span>  
  
### <a name="usedefaultwebproxy"></a><span data-ttu-id="72f2d-154">UseDefaultWebProxy</span><span class="sxs-lookup"><span data-stu-id="72f2d-154">UseDefaultWebProxy</span></span>  

 <span data-ttu-id="72f2d-155">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="72f2d-155">Data type: boolean</span></span>  
  
 <span data-ttu-id="72f2d-156">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="72f2d-156">Access type: Read-only</span></span>  
  
 <span data-ttu-id="72f2d-157">Un valor que indica si se utiliza la configuración de proxy del equipo en lugar de la configuración específica del usuario.</span><span class="sxs-lookup"><span data-stu-id="72f2d-157">A value that indicates whether the machine-wide proxy settings are used rather than the user specific settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72f2d-158">Requisitos</span><span class="sxs-lookup"><span data-stu-id="72f2d-158">Requirements</span></span>  
  
|<span data-ttu-id="72f2d-159">MOF</span><span class="sxs-lookup"><span data-stu-id="72f2d-159">MOF</span></span>|<span data-ttu-id="72f2d-160">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="72f2d-160">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="72f2d-161">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="72f2d-161">Namespace</span></span>|<span data-ttu-id="72f2d-162">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="72f2d-162">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="72f2d-163">Vea también</span><span class="sxs-lookup"><span data-stu-id="72f2d-163">See also</span></span>

- <xref:System.ServiceModel.Channels.HttpTransportBindingElement>
