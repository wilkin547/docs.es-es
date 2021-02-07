---
description: 'Más información acerca de: LocalServiceSecuritySettings'
title: LocalServiceSecuritySettings
ms.date: 03/30/2017
ms.assetid: 490aa0e5-5242-4f8d-b505-5ec6287633b4
ms.openlocfilehash: f7220e8253c6ab218414c1be7ed90e5d593b4692
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99743946"
---
# <a name="localservicesecuritysettings"></a><span data-ttu-id="8ba77-103">LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="8ba77-103">LocalServiceSecuritySettings</span></span>

<span data-ttu-id="8ba77-104">LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="8ba77-104">LocalServiceSecuritySettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ba77-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8ba77-105">Syntax</span></span>  
  
```csharp
class LocalServiceSecuritySettings  
{  
  boolean DetectReplays;  
  datetime InactivityTimeout;  
  datetime IssuedCookieLifetime;  
  sint32 MaxCachedCookies;  
  datetime MaxClockSkew;  
  sint32 MaxPendingSessions;  
  sint32 MaxStatefulNegotiations;  
  datetime NegotiationTimeout;  
  boolean ReconnectTransportOnFailure;  
  sint32 ReplayCacheSize;  
  datetime ReplayWindow;  
  datetime SessionKeyRenewalInterval;  
  datetime SessionKeyRolloverInterval;  
  datetime TimestampValidityDuration;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="8ba77-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="8ba77-106">Methods</span></span>  

 <span data-ttu-id="8ba77-107">La clase LocalServiceSecuritySettings no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="8ba77-107">The LocalServiceSecuritySettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="8ba77-108">Propiedades</span><span class="sxs-lookup"><span data-stu-id="8ba77-108">Properties</span></span>  

 <span data-ttu-id="8ba77-109">La clase LocalServiceSecuritySettings tiene las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="8ba77-109">The LocalServiceSecuritySettings class has the following properties:</span></span>  
  
### <a name="detectreplays"></a><span data-ttu-id="8ba77-110">DetectReplays</span><span class="sxs-lookup"><span data-stu-id="8ba77-110">DetectReplays</span></span>  

 <span data-ttu-id="8ba77-111">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="8ba77-111">Data type: boolean</span></span>  
  
 <span data-ttu-id="8ba77-112">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="8ba77-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8ba77-113">Un valor booleano que especifica si se detectan ataques de reproducción en el canal y si se abordan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="8ba77-113">A Boolean value that specifies whether replay attacks against the channel are detected and dealt with automatically.</span></span>  
  
### <a name="inactivitytimeout"></a><span data-ttu-id="8ba77-114">InactivityTimeout</span><span class="sxs-lookup"><span data-stu-id="8ba77-114">InactivityTimeout</span></span>  

 <span data-ttu-id="8ba77-115">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="8ba77-115">Data type: datetime</span></span>  
  
 <span data-ttu-id="8ba77-116">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="8ba77-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8ba77-117">El número máximo de sesiones de seguridad pendientes que el servicio admite.</span><span class="sxs-lookup"><span data-stu-id="8ba77-117">The maximum number of pending security sessions that the service supports.</span></span>  
  
### <a name="issuedcookielifetime"></a><span data-ttu-id="8ba77-118">IssuedCookieLifetime</span><span class="sxs-lookup"><span data-stu-id="8ba77-118">IssuedCookieLifetime</span></span>  

 <span data-ttu-id="8ba77-119">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="8ba77-119">Data type: datetime</span></span>  
  
 <span data-ttu-id="8ba77-120">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="8ba77-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8ba77-121">Un TimeSpan que especifica la duración emitida a todas las nuevas cookies de seguridad.</span><span class="sxs-lookup"><span data-stu-id="8ba77-121">A TimeSpan that specifies the lifetime issued to all new security cookies.</span></span>  
  
### <a name="maxcachedcookies"></a><span data-ttu-id="8ba77-122">MaxCachedCookies</span><span class="sxs-lookup"><span data-stu-id="8ba77-122">MaxCachedCookies</span></span>  

 <span data-ttu-id="8ba77-123">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="8ba77-123">Data type: sint32</span></span>  
  
 <span data-ttu-id="8ba77-124">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="8ba77-124">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8ba77-125">El número máximo de cookies que pueden estar almacenadas en memoria caché.</span><span class="sxs-lookup"><span data-stu-id="8ba77-125">The maximum number of cookies that can be cached.</span></span>  
  
### <a name="maxclockskew"></a><span data-ttu-id="8ba77-126">MaxClockSkew</span><span class="sxs-lookup"><span data-stu-id="8ba77-126">MaxClockSkew</span></span>  

 <span data-ttu-id="8ba77-127">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="8ba77-127">Data type: datetime</span></span>  
  
 <span data-ttu-id="8ba77-128">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="8ba77-128">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8ba77-129">Un TimeSpan que especifica la diferencia máxima de tiempo entre los relojes del sistema de las dos partes en comunicación.</span><span class="sxs-lookup"><span data-stu-id="8ba77-129">A TimeSpan that specifies the maximum time difference between the system clocks of the two communicating parties.</span></span>  
  
### <a name="maxpendingsessions"></a><span data-ttu-id="8ba77-130">MaxPendingSessions</span><span class="sxs-lookup"><span data-stu-id="8ba77-130">MaxPendingSessions</span></span>  

 <span data-ttu-id="8ba77-131">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="8ba77-131">Data type: sint32</span></span>  
  
 <span data-ttu-id="8ba77-132">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="8ba77-132">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8ba77-133">El número máximo de conexiones pendientes en el servicio.</span><span class="sxs-lookup"><span data-stu-id="8ba77-133">The maximum number of pending connections on the service.</span></span>  
  
### <a name="maxstatefulnegotiations"></a><span data-ttu-id="8ba77-134">MaxStatefulNegotiations</span><span class="sxs-lookup"><span data-stu-id="8ba77-134">MaxStatefulNegotiations</span></span>  

 <span data-ttu-id="8ba77-135">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="8ba77-135">Data type: sint32</span></span>  
  
 <span data-ttu-id="8ba77-136">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="8ba77-136">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8ba77-137">El número de negociaciones de seguridad que pueden estar activas de manera simultánea.</span><span class="sxs-lookup"><span data-stu-id="8ba77-137">The number of security negotiations that can be active concurrently.</span></span>  
  
### <a name="negotiationtimeout"></a><span data-ttu-id="8ba77-138">NegotiationTimeout</span><span class="sxs-lookup"><span data-stu-id="8ba77-138">NegotiationTimeout</span></span>  

 <span data-ttu-id="8ba77-139">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="8ba77-139">Data type: datetime</span></span>  
  
 <span data-ttu-id="8ba77-140">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="8ba77-140">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8ba77-141">Un TimeSpan que especifica la duración máxima para la fase de negociación de seguridad entre servidor y cliente.</span><span class="sxs-lookup"><span data-stu-id="8ba77-141">A TimeSpan that specifies the maximum duration for the security negotiation phase between server and client.</span></span>  
  
### <a name="reconnecttransportonfailure"></a><span data-ttu-id="8ba77-142">ReconnectTransportOnFailure</span><span class="sxs-lookup"><span data-stu-id="8ba77-142">ReconnectTransportOnFailure</span></span>  

 <span data-ttu-id="8ba77-143">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="8ba77-143">Data type: boolean</span></span>  
  
 <span data-ttu-id="8ba77-144">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="8ba77-144">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8ba77-145">Un valor booleano que especifica si las conexiones que usan mensajería WS-Reliable intentan volverse a conectar después de los errores de transporte.</span><span class="sxs-lookup"><span data-stu-id="8ba77-145">A Boolean value that specifies whether connections using WS-Reliable messaging attempt to reconnect after transport failures.</span></span>  
  
### <a name="replaycachesize"></a><span data-ttu-id="8ba77-146">ReplayCacheSize</span><span class="sxs-lookup"><span data-stu-id="8ba77-146">ReplayCacheSize</span></span>  

 <span data-ttu-id="8ba77-147">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="8ba77-147">Data type: sint32</span></span>  
  
 <span data-ttu-id="8ba77-148">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="8ba77-148">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8ba77-149">El número de valores de seguridad (nonce) almacenados en memoria caché usados para la detección de reproducción.</span><span class="sxs-lookup"><span data-stu-id="8ba77-149">The number of cached nonces used for replay detection.</span></span>  
  
### <a name="replaywindow"></a><span data-ttu-id="8ba77-150">ReplayWindow</span><span class="sxs-lookup"><span data-stu-id="8ba77-150">ReplayWindow</span></span>  

 <span data-ttu-id="8ba77-151">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="8ba77-151">Data type: datetime</span></span>  
  
 <span data-ttu-id="8ba77-152">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="8ba77-152">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8ba77-153">Un TimeSpan que especifica la duración en la que los nonces de mensajes particulares son válidos.</span><span class="sxs-lookup"><span data-stu-id="8ba77-153">A TimeSpan that specifies the duration in which individual message nonces are valid.</span></span>  
  
### <a name="sessionkeyrenewalinterval"></a><span data-ttu-id="8ba77-154">SessionKeyRenewalInterval</span><span class="sxs-lookup"><span data-stu-id="8ba77-154">SessionKeyRenewalInterval</span></span>  

 <span data-ttu-id="8ba77-155">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="8ba77-155">Data type: datetime</span></span>  
  
 <span data-ttu-id="8ba77-156">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="8ba77-156">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8ba77-157">Un TimeSpan que especifica la duración después de la cual el iniciador renueva la clave para la sesión de seguridad.</span><span class="sxs-lookup"><span data-stu-id="8ba77-157">A TimeSpan that specifies the duration after which the initiator renews the key for the security session.</span></span>  
  
### <a name="sessionkeyrolloverinterval"></a><span data-ttu-id="8ba77-158">SessionKeyRolloverInterval</span><span class="sxs-lookup"><span data-stu-id="8ba77-158">SessionKeyRolloverInterval</span></span>  

 <span data-ttu-id="8ba77-159">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="8ba77-159">Data type: datetime</span></span>  
  
 <span data-ttu-id="8ba77-160">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="8ba77-160">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8ba77-161">Un TimeSpan que especifica el intervalo de tiempo durante el cual una clave de sesión anterior es válida en mensajes entrantes durante una renovación de clave.</span><span class="sxs-lookup"><span data-stu-id="8ba77-161">A TimeSpan that specifies the time interval a previous session key is valid on incoming messages during a key renewal.</span></span>  
  
### <a name="timestampvalidityduration"></a><span data-ttu-id="8ba77-162">TimestampValidityDuration</span><span class="sxs-lookup"><span data-stu-id="8ba77-162">TimestampValidityDuration</span></span>  

 <span data-ttu-id="8ba77-163">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="8ba77-163">Data type: datetime</span></span>  
  
 <span data-ttu-id="8ba77-164">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="8ba77-164">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8ba77-165">Un TimeSpan positivo que especifica la duración en la que una marca de tiempo es válida.</span><span class="sxs-lookup"><span data-stu-id="8ba77-165">A TimeSpan that specifies the duration in which a time stamp is valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ba77-166">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8ba77-166">Requirements</span></span>  
  
|<span data-ttu-id="8ba77-167">MOF</span><span class="sxs-lookup"><span data-stu-id="8ba77-167">MOF</span></span>|<span data-ttu-id="8ba77-168">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="8ba77-168">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="8ba77-169">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="8ba77-169">Namespace</span></span>|<span data-ttu-id="8ba77-170">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="8ba77-170">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8ba77-171">Vea también</span><span class="sxs-lookup"><span data-stu-id="8ba77-171">See also</span></span>

- <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>
