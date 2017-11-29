---
title: "Función ConnectServerWmi (referencia de API no administrada)"
description: "La función ConnectServerWmi usa DCOM para crear una conexión a un espacio de nombres WMI."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: ConnectServerWmi
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: ConnectServerWmi
helpviewer_keywords: ConnectServerWmi function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b51050bce4603ebcfe99fb38d66e54683c677293
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2017
---
# <a name="connectserverwmi-function"></a><span data-ttu-id="84957-103">ConnectServerWmi (función)</span><span class="sxs-lookup"><span data-stu-id="84957-103">ConnectServerWmi function</span></span>
<span data-ttu-id="84957-104">Crea una conexión a través de DCOM a un espacio de nombres WMI en un equipo especificado.</span><span class="sxs-lookup"><span data-stu-id="84957-104">Creates a connection through DCOM to a WMI namespace on a specified computer.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="84957-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="84957-105">Syntax</span></span>  
  
```  
HRESULT ConnectServerWmi (
   [in] BSTR               strNetworkResource,
   [in] BSTR               strUser,
   [in] BSTR               strPassword,
   [in] BSTR               strLocale,
   [in] long               lSecurityFlags,
   [in] BSTR               strAuthority,
   [in] IWbemContext*      pCtx,
   [out] IWbemServices**   ppNamespace,
   [in] DWORD              impLevel, 
   [in] DWORD              authLevel
);
```  
## <a name="parameters"></a><span data-ttu-id="84957-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="84957-106">Parameters</span></span>

<span data-ttu-id="84957-107">`strNetworkResource`[in] Puntero a un válido `BSTR` que contiene la ruta de acceso del espacio de nombres WMI correcto.</span><span class="sxs-lookup"><span data-stu-id="84957-107">`strNetworkResource` [in] Pointer to a valid `BSTR` that contains the object path of the correct WMI namespace.</span></span> <span data-ttu-id="84957-108">Consulte la [comentarios](#remarks) sección para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="84957-108">See the [Remarks](#remarks) section for more information.</span></span>

<span data-ttu-id="84957-109">`strUser`[in] Un puntero a un válido `BSTR` que contiene el nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="84957-109">`strUser` [in] A pointer to a valid `BSTR` that contains the user name.</span></span> <span data-ttu-id="84957-110">Un `null` valor indica el contexto de seguridad actual.</span><span class="sxs-lookup"><span data-stu-id="84957-110">A `null` value indicates the current security context.</span></span> <span data-ttu-id="84957-111">Si el usuario es de un dominio distinto que el actual, `strUser` también pueden contener el nombre de usuario y de dominio separado por una barra diagonal inversa.</span><span class="sxs-lookup"><span data-stu-id="84957-111">If the user is from a different domain than the current one, `strUser` can also contain the domain and user name separated by a backslash.</span></span> <span data-ttu-id="84957-112">`strUser`También puede ser de usuario (UPN) de nombre principal dar formato, suhc como  *userName@domainName* .</span><span class="sxs-lookup"><span data-stu-id="84957-112">`strUser` can also be in user principal name (UPN) format, suhc as *userName@domainName*.</span></span> <span data-ttu-id="84957-113">Consulte la [comentarios](#remarks) sección para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="84957-113">See the [Remarks](#remarks) section for more information.</span></span>

<span data-ttu-id="84957-114">`strPassword`[in] Un puntero a un válido `BSTR` que contiene la contraseña.</span><span class="sxs-lookup"><span data-stu-id="84957-114">`strPassword` [in] A pointer to a valid `BSTR` that contains the password.</span></span> <span data-ttu-id="84957-115">Un `null` indica el contexto de seguridad actual.</span><span class="sxs-lookup"><span data-stu-id="84957-115">A `null` indicates the current security context.</span></span> <span data-ttu-id="84957-116">Una cadena vacía ("") indica que una contraseña válida de longitud cero.</span><span class="sxs-lookup"><span data-stu-id="84957-116">An empty string ("") indicates a valid zero-length password.</span></span>

<span data-ttu-id="84957-117">`strLocale`[in] Un puntero a un válido `BSTR` que indica la configuración regional correcta para la recuperación de información.</span><span class="sxs-lookup"><span data-stu-id="84957-117">`strLocale` [in] A pointer to a valid `BSTR` that indicates the correct locale for information retrieval.</span></span> <span data-ttu-id="84957-118">Para los identificadores de configuración regional de Microsoft, el formato de la cadena es "MS\_*xxx*", donde *xxx* es una cadena en formato hexadecimal que indica el identificador de configuración regional (LCID).</span><span class="sxs-lookup"><span data-stu-id="84957-118">For Microsoft locale identifiers, the format of the string is "MS\_*xxx*", where *xxx* is a string in hexadecimal form that indicates the locale identifier (LCID).</span></span> <span data-ttu-id="84957-119">Si se especifica una configuración regional no válido, el método devuelve `WBEM_E_INVALID_PARAMETER` excepto en Windows 7, donde la configuración regional predeterminada del servidor se utiliza en su lugar.</span><span class="sxs-lookup"><span data-stu-id="84957-119">If an invalid locale is specified, the method returns `WBEM_E_INVALID_PARAMETER` except on Windows 7, where the default locale of the server is used instead.</span></span> <span data-ttu-id="84957-120">Si ' se usa null1, la configuración regional actual.</span><span class="sxs-lookup"><span data-stu-id="84957-120">If \`null1, the current locale is used.</span></span> 
 
<span data-ttu-id="84957-121">`lSecurityFlags`[in] Marcas para pasar a la `ConnectServerWmi` método.</span><span class="sxs-lookup"><span data-stu-id="84957-121">`lSecurityFlags` [in] Flags to pass to the `ConnectServerWmi` method.</span></span> <span data-ttu-id="84957-122">Da como resultado un valor de cero (0) para este parámetro en la llamada a `ConnectServerWmi` devuelve solo una vez establecida una conexión con el servidor.</span><span class="sxs-lookup"><span data-stu-id="84957-122">A value of zero (0) for this parameter results in the call to `ConnectServerWmi` returning only after a connection to the server is established.</span></span> <span data-ttu-id="84957-123">Esto podría resultar en una aplicación no responde indefinidamente si el servidor se interrumpe.</span><span class="sxs-lookup"><span data-stu-id="84957-123">This could result in an application not responding indefinitely if the server is broken.</span></span> <span data-ttu-id="84957-124">Los otros valores válidos son:</span><span class="sxs-lookup"><span data-stu-id="84957-124">The other valid values are:</span></span>

| <span data-ttu-id="84957-125">Constante</span><span class="sxs-lookup"><span data-stu-id="84957-125">Constant</span></span>  | <span data-ttu-id="84957-126">Valor</span><span class="sxs-lookup"><span data-stu-id="84957-126">Value</span></span>  | <span data-ttu-id="84957-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="84957-127">Description</span></span>  |
|---------|---------|---------|
| `CONNECT_REPOSITORY_ONLY` | <span data-ttu-id="84957-128">0 x 40</span><span class="sxs-lookup"><span data-stu-id="84957-128">0x40</span></span> | <span data-ttu-id="84957-129">Reservado para uso interno.</span><span class="sxs-lookup"><span data-stu-id="84957-129">Reserved for internal use.</span></span> <span data-ttu-id="84957-130">No utilizar.</span><span class="sxs-lookup"><span data-stu-id="84957-130">Do not use.</span></span> |
| `WBEM_FLAG_CONNECT_USE_MAX_WAIT` | <span data-ttu-id="84957-131">0 x 80</span><span class="sxs-lookup"><span data-stu-id="84957-131">0x80</span></span> | <span data-ttu-id="84957-132">`ConnectServerWmi`se devuelve en dos minutos o menos.</span><span class="sxs-lookup"><span data-stu-id="84957-132">`ConnectServerWmi` returns in two minutes or less.</span></span> |

<span data-ttu-id="84957-133">`strAuthority`[in] El nombre de dominio del usuario.</span><span class="sxs-lookup"><span data-stu-id="84957-133">`strAuthority` [in] The domain name of the user.</span></span> <span data-ttu-id="84957-134">Puede tener los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="84957-134">It can have the following values:</span></span>

| <span data-ttu-id="84957-135">Valor</span><span class="sxs-lookup"><span data-stu-id="84957-135">Value</span></span> | <span data-ttu-id="84957-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="84957-136">Description</span></span> |
|---------|---------|
| <span data-ttu-id="84957-137">En blanco</span><span class="sxs-lookup"><span data-stu-id="84957-137">blank</span></span> | <span data-ttu-id="84957-138">Se utiliza la autenticación NTLM y se utiliza el dominio NTLM del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="84957-138">NTLM authentication is used, and the NTLM domain of the current user is used.</span></span> <span data-ttu-id="84957-139">Si `strUser` especifica el dominio (la ubicación recomendada), no debe especificarse aquí.</span><span class="sxs-lookup"><span data-stu-id="84957-139">If `strUser` specifies the domain (the recommended location), it must not be specified here.</span></span> <span data-ttu-id="84957-140">La función devuelve `WBEM_E_INVALID_PARAMETER` si se especifica el dominio en ambos parámetros.</span><span class="sxs-lookup"><span data-stu-id="84957-140">The function returns `WBEM_E_INVALID_PARAMETER` if you specify the domain in both parameters.</span></span> |
| <span data-ttu-id="84957-141">Kerberos:*nombre principal*</span><span class="sxs-lookup"><span data-stu-id="84957-141">Kerberos:*principal name*</span></span> | <span data-ttu-id="84957-142">Se utiliza la autenticación Kerberos, y este parámetro contiene un nombre principal de Kerberos.</span><span class="sxs-lookup"><span data-stu-id="84957-142">Kerberos authentication is used, and this parameter contains a Kerberos principal name.</span></span> |
| <span data-ttu-id="84957-143">NTLMDOMAIN:*nombre de dominio*</span><span class="sxs-lookup"><span data-stu-id="84957-143">NTLMDOMAIN:*domain name*</span></span> | <span data-ttu-id="84957-144">Se utiliza la autenticación de NT LAN Manager y este parámetro contiene un nombre de dominio NTLM.</span><span class="sxs-lookup"><span data-stu-id="84957-144">NT LAN Manager authentication is used, and this parameter contains an NTLM domain name.</span></span> |

`pCtx`   
<span data-ttu-id="84957-145">[in] Normalmente, este parámetro es `null`.</span><span class="sxs-lookup"><span data-stu-id="84957-145">[in] Typically, this parameter is is `null`.</span></span> <span data-ttu-id="84957-146">En caso contrario, es un puntero a un [IWbemContext](https://msdn.microsoft.com/library/aa391465%28v=vs.85%29.aspx) objeto requerido por uno o varios proveedores de clases dinámicas.</span><span class="sxs-lookup"><span data-stu-id="84957-146">Otherwise, it is a pointer to an [IWbemContext](https://msdn.microsoft.com/library/aa391465%28v=vs.85%29.aspx) object required by one or more dynamic class providers.</span></span> 

`ppNamespace`  
<span data-ttu-id="84957-147">[out] Cuando la función devuelve, recibe un puntero a un [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) objeto enlazado al espacio de nombres especificado.</span><span class="sxs-lookup"><span data-stu-id="84957-147">[out] When the function returns, receives a pointer to an [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) object bound to the specified namespace.</span></span> <span data-ttu-id="84957-148">Se establece para que apunte a `null` cuando se produce un error.</span><span class="sxs-lookup"><span data-stu-id="84957-148">It is set to point to `null` when there is an error.</span></span>

`impLevel`  
<span data-ttu-id="84957-149">[in] El nivel de suplantación.</span><span class="sxs-lookup"><span data-stu-id="84957-149">[in] The impersonation level.</span></span>

`authLevel`  
<span data-ttu-id="84957-150">[in] El nivel de autorización.</span><span class="sxs-lookup"><span data-stu-id="84957-150">[in] The authorization level.</span></span>

## <a name="return-value"></a><span data-ttu-id="84957-151">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="84957-151">Return value</span></span>

<span data-ttu-id="84957-152">Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, o bien puede definirlas como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="84957-152">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="84957-153">Constante</span><span class="sxs-lookup"><span data-stu-id="84957-153">Constant</span></span>  |<span data-ttu-id="84957-154">Valor</span><span class="sxs-lookup"><span data-stu-id="84957-154">Value</span></span>  |<span data-ttu-id="84957-155">Descripción</span><span class="sxs-lookup"><span data-stu-id="84957-155">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="84957-156">0 x 80041001</span><span class="sxs-lookup"><span data-stu-id="84957-156">0x80041001</span></span> | <span data-ttu-id="84957-157">Ha habido un error general.</span><span class="sxs-lookup"><span data-stu-id="84957-157">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="84957-158">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="84957-158">0x80041008</span></span> | <span data-ttu-id="84957-159">Un parámetro no es válido.</span><span class="sxs-lookup"><span data-stu-id="84957-159">A parameter is not valid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="84957-160">0 x 80041006</span><span class="sxs-lookup"><span data-stu-id="84957-160">0x80041006</span></span> | <span data-ttu-id="84957-161">No hay suficiente memoria disponible para completar la operación.</span><span class="sxs-lookup"><span data-stu-id="84957-161">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="84957-162">0</span><span class="sxs-lookup"><span data-stu-id="84957-162">0</span></span> | <span data-ttu-id="84957-163">La llamada de función tuvo éxito.</span><span class="sxs-lookup"><span data-stu-id="84957-163">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="84957-164">Comentarios</span><span class="sxs-lookup"><span data-stu-id="84957-164">Remarks</span></span>

<span data-ttu-id="84957-165">Esta función contiene una llamada a la [IWbemLocator:: ConnectServer](https://msdn.microsoft.com/libraryaa391769%28v=vs.85%29.aspx) método.</span><span class="sxs-lookup"><span data-stu-id="84957-165">This function wraps a call to the [IWbemLocator::ConnectServer](https://msdn.microsoft.com/libraryaa391769%28v=vs.85%29.aspx) method.</span></span>

 <span data-ttu-id="84957-166">Para el acceso local para el espacio de nombres predeterminado, `strNetworkResource` puede ser una ruta de acceso de objeto simple: "root\default" o "\\.\root\default".</span><span class="sxs-lookup"><span data-stu-id="84957-166">For local access to the default namespace, `strNetworkResource` can be a simple object path: "root\default" or "\\.\root\default".</span></span> <span data-ttu-id="84957-167">Para el acceso al espacio de nombres predeterminado en un equipo remoto mediante redes COM o compatible con Microsoft, incluir el nombre del equipo: "\\myserver\root\default".</span><span class="sxs-lookup"><span data-stu-id="84957-167">For access to the default namespace on a remote computer using COM or Microsoft-compatible networking, include the computer name: "\\myserver\root\default".</span></span> <span data-ttu-id="84957-168">El nombre del equipo también puede ser un nombre DNS o dirección IP.</span><span class="sxs-lookup"><span data-stu-id="84957-168">The computer name also can be a DNS name or IP address.</span></span> <span data-ttu-id="84957-169">El `ConnectServerWmi` función también puede conectar con equipos que ejecutan IPv6 mediante una dirección IPv6.</span><span class="sxs-lookup"><span data-stu-id="84957-169">The `ConnectServerWmi` function can also connect with computers running IPv6 using an IPv6 address.</span></span>

<span data-ttu-id="84957-170">`strUser`no puede ser una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="84957-170">`strUser` cannot be an empty string.</span></span> <span data-ttu-id="84957-171">Si se especifica el dominio en `strAuthority`, no también debe incluirse en `strUser`, o la función devuelve `WBEM_E_INVALID_PARAMETER`.</span><span class="sxs-lookup"><span data-stu-id="84957-171">If the domain is specified in `strAuthority`, it must not also be included in `strUser`, or the function returns `WBEM_E_INVALID_PARAMETER`.</span></span>


## <a name="requirements"></a><span data-ttu-id="84957-172">Requisitos</span><span class="sxs-lookup"><span data-stu-id="84957-172">Requirements</span></span>  
 <span data-ttu-id="84957-173">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84957-173">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84957-174">**Encabezado:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="84957-174">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="84957-175">**Versiones de .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="84957-175">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84957-176">Vea también</span><span class="sxs-lookup"><span data-stu-id="84957-176">See also</span></span>  
[<span data-ttu-id="84957-177">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="84957-177">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
