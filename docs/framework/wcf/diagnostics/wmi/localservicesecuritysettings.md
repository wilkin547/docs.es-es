---
title: LocalServiceSecuritySettings
ms.date: 03/30/2017
ms.assetid: 490aa0e5-5242-4f8d-b505-5ec6287633b4
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 8f80af782c474ccf3a232ab353125fa223d4f5d1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33486902"
---
# <a name="localservicesecuritysettings"></a><span data-ttu-id="24e94-102">LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="24e94-102">LocalServiceSecuritySettings</span></span>
<span data-ttu-id="24e94-103">LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="24e94-103">LocalServiceSecuritySettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24e94-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="24e94-104">Syntax</span></span>  
  
```  
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
  
## <a name="methods"></a><span data-ttu-id="24e94-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="24e94-105">Methods</span></span>  
 <span data-ttu-id="24e94-106">La clase LocalServiceSecuritySettings no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="24e94-106">The LocalServiceSecuritySettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="24e94-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="24e94-107">Properties</span></span>  
 <span data-ttu-id="24e94-108">La clase LocalServiceSecuritySettings tiene las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="24e94-108">The LocalServiceSecuritySettings class has the following properties:</span></span>  
  
### <a name="detectreplays"></a><span data-ttu-id="24e94-109">DetectReplays</span><span class="sxs-lookup"><span data-stu-id="24e94-109">DetectReplays</span></span>  
 <span data-ttu-id="24e94-110">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="24e94-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="24e94-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="24e94-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="24e94-112">Un valor booleano que especifica si se detectan ataques de reproducción en el canal y si se abordan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="24e94-112">A Boolean value that specifies whether replay attacks against the channel are detected and dealt with automatically.</span></span>  
  
### <a name="inactivitytimeout"></a><span data-ttu-id="24e94-113">InactivityTimeout</span><span class="sxs-lookup"><span data-stu-id="24e94-113">InactivityTimeout</span></span>  
 <span data-ttu-id="24e94-114">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="24e94-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="24e94-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="24e94-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="24e94-116">El número máximo de sesiones de seguridad pendientes que el servicio admite.</span><span class="sxs-lookup"><span data-stu-id="24e94-116">The maximum number of pending security sessions that the service supports.</span></span>  
  
### <a name="issuedcookielifetime"></a><span data-ttu-id="24e94-117">IssuedCookieLifetime</span><span class="sxs-lookup"><span data-stu-id="24e94-117">IssuedCookieLifetime</span></span>  
 <span data-ttu-id="24e94-118">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="24e94-118">Data type: datetime</span></span>  
  
 <span data-ttu-id="24e94-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="24e94-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="24e94-120">Un TimeSpan que especifica la duración emitida a todas las nuevas cookies de seguridad.</span><span class="sxs-lookup"><span data-stu-id="24e94-120">A TimeSpan that specifies the lifetime issued to all new security cookies.</span></span>  
  
### <a name="maxcachedcookies"></a><span data-ttu-id="24e94-121">MaxCachedCookies</span><span class="sxs-lookup"><span data-stu-id="24e94-121">MaxCachedCookies</span></span>  
 <span data-ttu-id="24e94-122">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="24e94-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="24e94-123">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="24e94-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="24e94-124">El número máximo de cookies que pueden estar almacenadas en memoria caché.</span><span class="sxs-lookup"><span data-stu-id="24e94-124">The maximum number of cookies that can be cached.</span></span>  
  
### <a name="maxclockskew"></a><span data-ttu-id="24e94-125">MaxClockSkew</span><span class="sxs-lookup"><span data-stu-id="24e94-125">MaxClockSkew</span></span>  
 <span data-ttu-id="24e94-126">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="24e94-126">Data type: datetime</span></span>  
  
 <span data-ttu-id="24e94-127">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="24e94-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="24e94-128">Un TimeSpan que especifica la diferencia máxima de tiempo entre los relojes del sistema de las dos partes en comunicación.</span><span class="sxs-lookup"><span data-stu-id="24e94-128">A TimeSpan that specifies the maximum time difference between the system clocks of the two communicating parties.</span></span>  
  
### <a name="maxpendingsessions"></a><span data-ttu-id="24e94-129">MaxPendingSessions</span><span class="sxs-lookup"><span data-stu-id="24e94-129">MaxPendingSessions</span></span>  
 <span data-ttu-id="24e94-130">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="24e94-130">Data type: sint32</span></span>  
  
 <span data-ttu-id="24e94-131">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="24e94-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="24e94-132">El número máximo de conexiones pendientes en el servicio.</span><span class="sxs-lookup"><span data-stu-id="24e94-132">The maximum number of pending connections on the service.</span></span>  
  
### <a name="maxstatefulnegotiations"></a><span data-ttu-id="24e94-133">MaxStatefulNegotiations</span><span class="sxs-lookup"><span data-stu-id="24e94-133">MaxStatefulNegotiations</span></span>  
 <span data-ttu-id="24e94-134">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="24e94-134">Data type: sint32</span></span>  
  
 <span data-ttu-id="24e94-135">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="24e94-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="24e94-136">El número de negociaciones de seguridad que pueden estar activas de manera simultánea.</span><span class="sxs-lookup"><span data-stu-id="24e94-136">The number of security negotiations that can be active concurrently.</span></span>  
  
### <a name="negotiationtimeout"></a><span data-ttu-id="24e94-137">NegotiationTimeout</span><span class="sxs-lookup"><span data-stu-id="24e94-137">NegotiationTimeout</span></span>  
 <span data-ttu-id="24e94-138">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="24e94-138">Data type: datetime</span></span>  
  
 <span data-ttu-id="24e94-139">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="24e94-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="24e94-140">Un TimeSpan que especifica la duración máxima para la fase de negociación de seguridad entre servidor y cliente.</span><span class="sxs-lookup"><span data-stu-id="24e94-140">A TimeSpan that specifies the maximum duration for the security negotiation phase between server and client.</span></span>  
  
### <a name="reconnecttransportonfailure"></a><span data-ttu-id="24e94-141">ReconnectTransportOnFailure</span><span class="sxs-lookup"><span data-stu-id="24e94-141">ReconnectTransportOnFailure</span></span>  
 <span data-ttu-id="24e94-142">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="24e94-142">Data type: boolean</span></span>  
  
 <span data-ttu-id="24e94-143">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="24e94-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="24e94-144">Un valor booleano que especifica si las conexiones que usan mensajería WS-Reliable intentan volverse a conectar después de los errores de transporte.</span><span class="sxs-lookup"><span data-stu-id="24e94-144">A Boolean value that specifies whether connections using WS-Reliable messaging attempt to reconnect after transport failures.</span></span>  
  
### <a name="replaycachesize"></a><span data-ttu-id="24e94-145">ReplayCacheSize</span><span class="sxs-lookup"><span data-stu-id="24e94-145">ReplayCacheSize</span></span>  
 <span data-ttu-id="24e94-146">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="24e94-146">Data type: sint32</span></span>  
  
 <span data-ttu-id="24e94-147">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="24e94-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="24e94-148">El número de valores de seguridad (nonce) almacenados en memoria caché usados para la detección de reproducción.</span><span class="sxs-lookup"><span data-stu-id="24e94-148">The number of cached nonces used for replay detection.</span></span>  
  
### <a name="replaywindow"></a><span data-ttu-id="24e94-149">ReplayWindow</span><span class="sxs-lookup"><span data-stu-id="24e94-149">ReplayWindow</span></span>  
 <span data-ttu-id="24e94-150">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="24e94-150">Data type: datetime</span></span>  
  
 <span data-ttu-id="24e94-151">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="24e94-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="24e94-152">Un TimeSpan que especifica la duración en la que los nonces de mensajes particulares son válidos.</span><span class="sxs-lookup"><span data-stu-id="24e94-152">A TimeSpan that specifies the duration in which individual message nonces are valid.</span></span>  
  
### <a name="sessionkeyrenewalinterval"></a><span data-ttu-id="24e94-153">SessionKeyRenewalInterval</span><span class="sxs-lookup"><span data-stu-id="24e94-153">SessionKeyRenewalInterval</span></span>  
 <span data-ttu-id="24e94-154">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="24e94-154">Data type: datetime</span></span>  
  
 <span data-ttu-id="24e94-155">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="24e94-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="24e94-156">Un TimeSpan que especifica la duración después de la cual el iniciador renueva la clave para la sesión de seguridad.</span><span class="sxs-lookup"><span data-stu-id="24e94-156">A TimeSpan that specifies the duration after which the initiator renews the key for the security session.</span></span>  
  
### <a name="sessionkeyrolloverinterval"></a><span data-ttu-id="24e94-157">SessionKeyRolloverInterval</span><span class="sxs-lookup"><span data-stu-id="24e94-157">SessionKeyRolloverInterval</span></span>  
 <span data-ttu-id="24e94-158">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="24e94-158">Data type: datetime</span></span>  
  
 <span data-ttu-id="24e94-159">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="24e94-159">Access type: Read-only</span></span>  
  
 <span data-ttu-id="24e94-160">Un TimeSpan que especifica el intervalo de tiempo durante el cual una clave de sesión anterior es válida en mensajes entrantes durante una renovación de clave.</span><span class="sxs-lookup"><span data-stu-id="24e94-160">A TimeSpan that specifies the time interval a previous session key is valid on incoming messages during a key renewal.</span></span>  
  
### <a name="timestampvalidityduration"></a><span data-ttu-id="24e94-161">TimestampValidityDuration</span><span class="sxs-lookup"><span data-stu-id="24e94-161">TimestampValidityDuration</span></span>  
 <span data-ttu-id="24e94-162">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="24e94-162">Data type: datetime</span></span>  
  
 <span data-ttu-id="24e94-163">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="24e94-163">Access type: Read-only</span></span>  
  
 <span data-ttu-id="24e94-164">Un TimeSpan positivo que especifica la duración en la que una marca de tiempo es válida.</span><span class="sxs-lookup"><span data-stu-id="24e94-164">A TimeSpan that specifies the duration in which a time stamp is valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24e94-165">Requisitos</span><span class="sxs-lookup"><span data-stu-id="24e94-165">Requirements</span></span>  
  
|<span data-ttu-id="24e94-166">MOF</span><span class="sxs-lookup"><span data-stu-id="24e94-166">MOF</span></span>|<span data-ttu-id="24e94-167">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="24e94-167">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="24e94-168">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="24e94-168">Namespace</span></span>|<span data-ttu-id="24e94-169">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="24e94-169">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="24e94-170">Vea también</span><span class="sxs-lookup"><span data-stu-id="24e94-170">See Also</span></span>  
 <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>
