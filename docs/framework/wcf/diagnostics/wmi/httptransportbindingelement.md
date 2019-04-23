---
title: HttpTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 088a7bce-6bb2-4839-ad74-f68d4b1aa0f9
ms.openlocfilehash: 5e23342d57621554aaec67c5c568bb75202a9454
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2019
ms.locfileid: "59977046"
---
# <a name="httptransportbindingelement"></a><span data-ttu-id="bc565-102">HttpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="bc565-102">HttpTransportBindingElement</span></span>
<span data-ttu-id="bc565-103">HttpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="bc565-103">HttpTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc565-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bc565-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="bc565-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="bc565-105">Methods</span></span>  
 <span data-ttu-id="bc565-106">La clase HttpTransportBindingElement no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="bc565-106">The HttpTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="bc565-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="bc565-107">Properties</span></span>  
 <span data-ttu-id="bc565-108">La clase HttpTransportBindingElement tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="bc565-108">The HttpTransportBindingElement class has the following properties:</span></span>  
  
### <a name="allowcookies"></a><span data-ttu-id="bc565-109">AllowCookies</span><span class="sxs-lookup"><span data-stu-id="bc565-109">AllowCookies</span></span>  
 <span data-ttu-id="bc565-110">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="bc565-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="bc565-111">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="bc565-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bc565-112">Un valor que indica si el cliente acepta las cookies y las propaga en solicitudes futuras.</span><span class="sxs-lookup"><span data-stu-id="bc565-112">A value that indicates whether the client accepts cookies and propagates them on future requests.</span></span>  
  
### <a name="authenticationscheme"></a><span data-ttu-id="bc565-113">AuthenticationScheme</span><span class="sxs-lookup"><span data-stu-id="bc565-113">AuthenticationScheme</span></span>  
 <span data-ttu-id="bc565-114">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="bc565-114">Data type: string</span></span>  
  
 <span data-ttu-id="bc565-115">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="bc565-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bc565-116">El esquema de autenticación usado para autenticar las solicitudes del cliente que está procesando un agente de escucha HTTP.</span><span class="sxs-lookup"><span data-stu-id="bc565-116">The authentication scheme used to authenticate client requests being processed by an HTTP listener.</span></span>  
  
### <a name="bypassproxyonlocal"></a><span data-ttu-id="bc565-117">BypassProxyOnLocal</span><span class="sxs-lookup"><span data-stu-id="bc565-117">BypassProxyOnLocal</span></span>  
 <span data-ttu-id="bc565-118">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="bc565-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="bc565-119">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="bc565-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bc565-120">Un valor que indica si se omiten servidores proxy para direcciones locales.</span><span class="sxs-lookup"><span data-stu-id="bc565-120">A value that indicates whether proxies are ignored for local addresses.</span></span>  
  
### <a name="hostnamecomparisonmode"></a><span data-ttu-id="bc565-121">HostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="bc565-121">HostNameComparisonMode</span></span>  
 <span data-ttu-id="bc565-122">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="bc565-122">Data type: string</span></span>  
  
 <span data-ttu-id="bc565-123">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="bc565-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bc565-124">Un valor que indica si el nombre del host se usa para alcanzar el servicio al coincidir con el URI.</span><span class="sxs-lookup"><span data-stu-id="bc565-124">A value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>  
  
### <a name="keepaliveenabled"></a><span data-ttu-id="bc565-125">KeepAliveEnabled</span><span class="sxs-lookup"><span data-stu-id="bc565-125">KeepAliveEnabled</span></span>  
 <span data-ttu-id="bc565-126">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="bc565-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="bc565-127">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="bc565-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bc565-128">Cuando se habilita, las conexiones HTTP se mantienen vivas sin tener en cuenta el nivel de actividad.</span><span class="sxs-lookup"><span data-stu-id="bc565-128">When enabled, HTTP connections are kept alive regardless of activity level.</span></span>  
  
### <a name="maxbuffersize"></a><span data-ttu-id="bc565-129">MaxBufferSize</span><span class="sxs-lookup"><span data-stu-id="bc565-129">MaxBufferSize</span></span>  
 <span data-ttu-id="bc565-130">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="bc565-130">Data type: sint32</span></span>  
  
 <span data-ttu-id="bc565-131">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="bc565-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bc565-132">El tamaño máximo del grupo de búferes.</span><span class="sxs-lookup"><span data-stu-id="bc565-132">The maximum size of the buffer pool.</span></span>  
  
### <a name="proxyaddress"></a><span data-ttu-id="bc565-133">ProxyAddress</span><span class="sxs-lookup"><span data-stu-id="bc565-133">ProxyAddress</span></span>  
 <span data-ttu-id="bc565-134">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="bc565-134">Data type: string</span></span>  
  
 <span data-ttu-id="bc565-135">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="bc565-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bc565-136">Un URI que contiene la dirección del proxy que utilizar para las solicitudes HTTP.</span><span class="sxs-lookup"><span data-stu-id="bc565-136">A URI that contains the address of the proxy to use for HTTP requests.</span></span>  
  
### <a name="proxyauthenticationscheme"></a><span data-ttu-id="bc565-137">ProxyAuthenticationScheme</span><span class="sxs-lookup"><span data-stu-id="bc565-137">ProxyAuthenticationScheme</span></span>  
 <span data-ttu-id="bc565-138">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="bc565-138">Data type: string</span></span>  
  
 <span data-ttu-id="bc565-139">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="bc565-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bc565-140">El esquema de autenticación usado para autenticar las solicitudes del cliente que un proxy HTTP está procesando.</span><span class="sxs-lookup"><span data-stu-id="bc565-140">The authentication scheme used to authenticate client requests being processed by an HTTP proxy.</span></span>  
  
### <a name="realm"></a><span data-ttu-id="bc565-141">Dominio kerberos</span><span class="sxs-lookup"><span data-stu-id="bc565-141">Realm</span></span>  
 <span data-ttu-id="bc565-142">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="bc565-142">Data type: string</span></span>  
  
 <span data-ttu-id="bc565-143">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="bc565-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bc565-144">El dominio kerberos de autenticación.</span><span class="sxs-lookup"><span data-stu-id="bc565-144">The authentication realm.</span></span>  
  
### <a name="transfermode"></a><span data-ttu-id="bc565-145">TransferMode</span><span class="sxs-lookup"><span data-stu-id="bc565-145">TransferMode</span></span>  
 <span data-ttu-id="bc565-146">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="bc565-146">Data type: string</span></span>  
  
 <span data-ttu-id="bc565-147">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="bc565-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bc565-148">Un valor que especifica si los mensajes se almacenan en búfer, se transmiten o si son una solicitud o una respuesta.</span><span class="sxs-lookup"><span data-stu-id="bc565-148">A value that specifies whether messages are buffered or streamed or a request or response.</span></span>  
  
### <a name="unsafeconnectionntlmauthentication"></a><span data-ttu-id="bc565-149">UnsafeConnectionNtlmAuthentication</span><span class="sxs-lookup"><span data-stu-id="bc565-149">UnsafeConnectionNtlmAuthentication</span></span>  
 <span data-ttu-id="bc565-150">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="bc565-150">Data type: boolean</span></span>  
  
 <span data-ttu-id="bc565-151">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="bc565-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bc565-152">Un valor que indica si la conexión compartida no segura está habilitada en el servidor.</span><span class="sxs-lookup"><span data-stu-id="bc565-152">A value that indicates whether Unsafe Connection Sharing is enabled on the server.</span></span>  
  
### <a name="usedefaultwebproxy"></a><span data-ttu-id="bc565-153">UseDefaultWebProxy</span><span class="sxs-lookup"><span data-stu-id="bc565-153">UseDefaultWebProxy</span></span>  
 <span data-ttu-id="bc565-154">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="bc565-154">Data type: boolean</span></span>  
  
 <span data-ttu-id="bc565-155">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="bc565-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bc565-156">Un valor que indica si se utiliza la configuración de proxy del equipo en lugar de la configuración específica del usuario.</span><span class="sxs-lookup"><span data-stu-id="bc565-156">A value that indicates whether the machine-wide proxy settings are used rather than the user specific settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc565-157">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bc565-157">Requirements</span></span>  
  
|<span data-ttu-id="bc565-158">MOF</span><span class="sxs-lookup"><span data-stu-id="bc565-158">MOF</span></span>|<span data-ttu-id="bc565-159">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="bc565-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="bc565-160">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="bc565-160">Namespace</span></span>|<span data-ttu-id="bc565-161">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="bc565-161">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bc565-162">Vea también</span><span class="sxs-lookup"><span data-stu-id="bc565-162">See also</span></span>

- <xref:System.ServiceModel.Channels.HttpTransportBindingElement>
