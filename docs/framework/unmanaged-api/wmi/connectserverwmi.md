---
title: Función ConnectServerWmi (referencia de API no administrada)
description: La función ConnectServerWmi usa DCOM para crear una conexión a un espacio de nombres WMI.
ms.date: 11/06/2017
api_name:
- ConnectServerWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ConnectServerWmi
helpviewer_keywords:
- ConnectServerWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 163e61eef8a753b5b6470285e5e3ce63789e25a4
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43416142"
---
# <a name="connectserverwmi-function"></a><span data-ttu-id="2e570-103">Función ConnectServerWmi</span><span class="sxs-lookup"><span data-stu-id="2e570-103">ConnectServerWmi function</span></span>
<span data-ttu-id="2e570-104">Crea una conexión a través de DCOM para un espacio de nombres WMI en un equipo especificado.</span><span class="sxs-lookup"><span data-stu-id="2e570-104">Creates a connection through DCOM to a WMI namespace on a specified computer.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="2e570-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2e570-105">Syntax</span></span>  
  
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
## <a name="parameters"></a><span data-ttu-id="2e570-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2e570-106">Parameters</span></span>

<span data-ttu-id="2e570-107">`strNetworkResource` [in] Puntero a una `BSTR` que contiene la ruta de acceso del espacio de nombres WMI correcto.</span><span class="sxs-lookup"><span data-stu-id="2e570-107">`strNetworkResource` [in] Pointer to a valid `BSTR` that contains the object path of the correct WMI namespace.</span></span> <span data-ttu-id="2e570-108">Consulte la [comentarios](#remarks) sección para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="2e570-108">See the [Remarks](#remarks) section for more information.</span></span>

<span data-ttu-id="2e570-109">`strUser` [in] Un puntero a una `BSTR` que contiene el nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="2e570-109">`strUser` [in] A pointer to a valid `BSTR` that contains the user name.</span></span> <span data-ttu-id="2e570-110">Un `null` valor indica el contexto de seguridad actual.</span><span class="sxs-lookup"><span data-stu-id="2e570-110">A `null` value indicates the current security context.</span></span> <span data-ttu-id="2e570-111">Si el usuario es de un dominio diferente que el actual, `strUser` también puede contener el nombre de usuario y dominio separado por una barra diagonal inversa.</span><span class="sxs-lookup"><span data-stu-id="2e570-111">If the user is from a different domain than the current one, `strUser` can also contain the domain and user name separated by a backslash.</span></span> <span data-ttu-id="2e570-112">`strUser` También puede ser de usuario (UPN) del nombre principal dar formato, suhc como *userName@domainName*.</span><span class="sxs-lookup"><span data-stu-id="2e570-112">`strUser` can also be in user principal name (UPN) format, suhc as *userName@domainName*.</span></span> <span data-ttu-id="2e570-113">Consulte la [comentarios](#remarks) sección para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="2e570-113">See the [Remarks](#remarks) section for more information.</span></span>

<span data-ttu-id="2e570-114">`strPassword` [in] Un puntero a una `BSTR` que contiene la contraseña.</span><span class="sxs-lookup"><span data-stu-id="2e570-114">`strPassword` [in] A pointer to a valid `BSTR` that contains the password.</span></span> <span data-ttu-id="2e570-115">Un `null` indica el contexto de seguridad actual.</span><span class="sxs-lookup"><span data-stu-id="2e570-115">A `null` indicates the current security context.</span></span> <span data-ttu-id="2e570-116">Una cadena vacía ("") indica que una contraseña válida de longitud cero.</span><span class="sxs-lookup"><span data-stu-id="2e570-116">An empty string ("") indicates a valid zero-length password.</span></span>

<span data-ttu-id="2e570-117">`strLocale` [in] Un puntero a una `BSTR` que indica la configuración regional correcta para la recuperación de información.</span><span class="sxs-lookup"><span data-stu-id="2e570-117">`strLocale` [in] A pointer to a valid `BSTR` that indicates the correct locale for information retrieval.</span></span> <span data-ttu-id="2e570-118">Para los identificadores de configuración regional de Microsoft, el formato de la cadena es "MS\_*xxx*", donde *xxx* es una cadena en formato hexadecimal que indica el identificador de configuración regional (LCID).</span><span class="sxs-lookup"><span data-stu-id="2e570-118">For Microsoft locale identifiers, the format of the string is "MS\_*xxx*", where *xxx* is a string in hexadecimal form that indicates the locale identifier (LCID).</span></span> <span data-ttu-id="2e570-119">Si se especifica una configuración regional no válido, el método devuelve `WBEM_E_INVALID_PARAMETER` excepto en Windows 7, donde la configuración regional predeterminada del servidor se usa en su lugar.</span><span class="sxs-lookup"><span data-stu-id="2e570-119">If an invalid locale is specified, the method returns `WBEM_E_INVALID_PARAMETER` except on Windows 7, where the default locale of the server is used instead.</span></span> <span data-ttu-id="2e570-120">Si ' se usa null1, la configuración regional actual.</span><span class="sxs-lookup"><span data-stu-id="2e570-120">If \`null1, the current locale is used.</span></span> 
 
<span data-ttu-id="2e570-121">`lSecurityFlags` [in] Marcas para pasar a la `ConnectServerWmi` método.</span><span class="sxs-lookup"><span data-stu-id="2e570-121">`lSecurityFlags` [in] Flags to pass to the `ConnectServerWmi` method.</span></span> <span data-ttu-id="2e570-122">Da como resultado un valor de cero (0) para este parámetro en la llamada a `ConnectServerWmi` devolver solo una vez establecida una conexión al servidor.</span><span class="sxs-lookup"><span data-stu-id="2e570-122">A value of zero (0) for this parameter results in the call to `ConnectServerWmi` returning only after a connection to the server is established.</span></span> <span data-ttu-id="2e570-123">Esto podría dar lugar a una aplicación no responde indefinidamente si el servidor se interrumpe.</span><span class="sxs-lookup"><span data-stu-id="2e570-123">This could result in an application not responding indefinitely if the server is broken.</span></span> <span data-ttu-id="2e570-124">Los otros valores válidos son:</span><span class="sxs-lookup"><span data-stu-id="2e570-124">The other valid values are:</span></span>

| <span data-ttu-id="2e570-125">Constante</span><span class="sxs-lookup"><span data-stu-id="2e570-125">Constant</span></span>  | <span data-ttu-id="2e570-126">Valor</span><span class="sxs-lookup"><span data-stu-id="2e570-126">Value</span></span>  | <span data-ttu-id="2e570-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="2e570-127">Description</span></span>  |
|---------|---------|---------|
| `CONNECT_REPOSITORY_ONLY` | <span data-ttu-id="2e570-128">0x40</span><span class="sxs-lookup"><span data-stu-id="2e570-128">0x40</span></span> | <span data-ttu-id="2e570-129">Reservado para uso interno.</span><span class="sxs-lookup"><span data-stu-id="2e570-129">Reserved for internal use.</span></span> <span data-ttu-id="2e570-130">No utilizar.</span><span class="sxs-lookup"><span data-stu-id="2e570-130">Do not use.</span></span> |
| `WBEM_FLAG_CONNECT_USE_MAX_WAIT` | <span data-ttu-id="2e570-131">0x80</span><span class="sxs-lookup"><span data-stu-id="2e570-131">0x80</span></span> | <span data-ttu-id="2e570-132">`ConnectServerWmi` se devuelve en dos minutos o menos.</span><span class="sxs-lookup"><span data-stu-id="2e570-132">`ConnectServerWmi` returns in two minutes or less.</span></span> |

<span data-ttu-id="2e570-133">`strAuthority` [in] El nombre de dominio del usuario.</span><span class="sxs-lookup"><span data-stu-id="2e570-133">`strAuthority` [in] The domain name of the user.</span></span> <span data-ttu-id="2e570-134">Puede tener los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="2e570-134">It can have the following values:</span></span>

| <span data-ttu-id="2e570-135">Valor</span><span class="sxs-lookup"><span data-stu-id="2e570-135">Value</span></span> | <span data-ttu-id="2e570-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="2e570-136">Description</span></span> |
|---------|---------|
| <span data-ttu-id="2e570-137">En blanco</span><span class="sxs-lookup"><span data-stu-id="2e570-137">blank</span></span> | <span data-ttu-id="2e570-138">Se usa la autenticación NTLM y se utiliza el dominio NTLM del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="2e570-138">NTLM authentication is used, and the NTLM domain of the current user is used.</span></span> <span data-ttu-id="2e570-139">Si `strUser` especifica el dominio (la ubicación recomendada), no debe especificarse aquí.</span><span class="sxs-lookup"><span data-stu-id="2e570-139">If `strUser` specifies the domain (the recommended location), it must not be specified here.</span></span> <span data-ttu-id="2e570-140">La función devuelve `WBEM_E_INVALID_PARAMETER` si especifica el dominio en los dos parámetros.</span><span class="sxs-lookup"><span data-stu-id="2e570-140">The function returns `WBEM_E_INVALID_PARAMETER` if you specify the domain in both parameters.</span></span> |
| <span data-ttu-id="2e570-141">Kerberos:*nombre principal*</span><span class="sxs-lookup"><span data-stu-id="2e570-141">Kerberos:*principal name*</span></span> | <span data-ttu-id="2e570-142">Se utiliza la autenticación Kerberos, y este parámetro contiene un nombre principal de Kerberos.</span><span class="sxs-lookup"><span data-stu-id="2e570-142">Kerberos authentication is used, and this parameter contains a Kerberos principal name.</span></span> |
| <span data-ttu-id="2e570-143">NTLMDOMAIN:*nombre de dominio*</span><span class="sxs-lookup"><span data-stu-id="2e570-143">NTLMDOMAIN:*domain name*</span></span> | <span data-ttu-id="2e570-144">Se utiliza la autenticación NT LAN Manager y este parámetro contiene un nombre de dominio NTLM.</span><span class="sxs-lookup"><span data-stu-id="2e570-144">NT LAN Manager authentication is used, and this parameter contains an NTLM domain name.</span></span> |

`pCtx`   
<span data-ttu-id="2e570-145">[in] Normalmente, este parámetro es `null`.</span><span class="sxs-lookup"><span data-stu-id="2e570-145">[in] Typically, this parameter is is `null`.</span></span> <span data-ttu-id="2e570-146">En caso contrario, es un puntero a un [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) objeto requerido por uno o varios proveedores de la clase dinámica.</span><span class="sxs-lookup"><span data-stu-id="2e570-146">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) object required by one or more dynamic class providers.</span></span> 

`ppNamespace`  
<span data-ttu-id="2e570-147">[out] Devuelve la función recibe un puntero a un [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) objeto enlazado al espacio de nombres especificado.</span><span class="sxs-lookup"><span data-stu-id="2e570-147">[out] When the function returns, receives a pointer to an [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object bound to the specified namespace.</span></span> <span data-ttu-id="2e570-148">Se establece para que apunte a `null` cuando se produce un error.</span><span class="sxs-lookup"><span data-stu-id="2e570-148">It is set to point to `null` when there is an error.</span></span>

`impLevel`  
<span data-ttu-id="2e570-149">[in] El nivel de suplantación.</span><span class="sxs-lookup"><span data-stu-id="2e570-149">[in] The impersonation level.</span></span>

`authLevel`  
<span data-ttu-id="2e570-150">[in] El nivel de autorización.</span><span class="sxs-lookup"><span data-stu-id="2e570-150">[in] The authorization level.</span></span>

## <a name="return-value"></a><span data-ttu-id="2e570-151">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2e570-151">Return value</span></span>

<span data-ttu-id="2e570-152">Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="2e570-152">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="2e570-153">Constante</span><span class="sxs-lookup"><span data-stu-id="2e570-153">Constant</span></span>  |<span data-ttu-id="2e570-154">Valor</span><span class="sxs-lookup"><span data-stu-id="2e570-154">Value</span></span>  |<span data-ttu-id="2e570-155">Descripción</span><span class="sxs-lookup"><span data-stu-id="2e570-155">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="2e570-156">0 x 80041001</span><span class="sxs-lookup"><span data-stu-id="2e570-156">0x80041001</span></span> | <span data-ttu-id="2e570-157">Ha habido un error general.</span><span class="sxs-lookup"><span data-stu-id="2e570-157">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="2e570-158">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="2e570-158">0x80041008</span></span> | <span data-ttu-id="2e570-159">Un parámetro no es válido.</span><span class="sxs-lookup"><span data-stu-id="2e570-159">A parameter is not valid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="2e570-160">0 x 80041006</span><span class="sxs-lookup"><span data-stu-id="2e570-160">0x80041006</span></span> | <span data-ttu-id="2e570-161">No hay suficiente memoria disponible para completar la operación.</span><span class="sxs-lookup"><span data-stu-id="2e570-161">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="2e570-162">0</span><span class="sxs-lookup"><span data-stu-id="2e570-162">0</span></span> | <span data-ttu-id="2e570-163">La llamada de función fue correcta.</span><span class="sxs-lookup"><span data-stu-id="2e570-163">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="2e570-164">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2e570-164">Remarks</span></span>

<span data-ttu-id="2e570-165">Esta función contiene una llamada a la [IWbemLocator:: ConnectServer](https://msdn.microsoft.com/libraryaa391769%28v=vs.85%29.aspx) método.</span><span class="sxs-lookup"><span data-stu-id="2e570-165">This function wraps a call to the [IWbemLocator::ConnectServer](https://msdn.microsoft.com/libraryaa391769%28v=vs.85%29.aspx) method.</span></span>

 <span data-ttu-id="2e570-166">Para el acceso local al espacio de nombres predeterminado, `strNetworkResource` puede ser una ruta de acceso de objeto simple: "root\default" o "\\.\root\default".</span><span class="sxs-lookup"><span data-stu-id="2e570-166">For local access to the default namespace, `strNetworkResource` can be a simple object path: "root\default" or "\\.\root\default".</span></span> <span data-ttu-id="2e570-167">Para el acceso al espacio de nombres predeterminado en un equipo remoto mediante redes de COM o compatible con Microsoft, incluya el nombre del equipo: "\\myserver\root\default".</span><span class="sxs-lookup"><span data-stu-id="2e570-167">For access to the default namespace on a remote computer using COM or Microsoft-compatible networking, include the computer name: "\\myserver\root\default".</span></span> <span data-ttu-id="2e570-168">El nombre del equipo también puede ser un nombre DNS o dirección IP.</span><span class="sxs-lookup"><span data-stu-id="2e570-168">The computer name also can be a DNS name or IP address.</span></span> <span data-ttu-id="2e570-169">El `ConnectServerWmi` función también puede conectar con equipos que ejecutan IPv6 mediante una dirección IPv6.</span><span class="sxs-lookup"><span data-stu-id="2e570-169">The `ConnectServerWmi` function can also connect with computers running IPv6 using an IPv6 address.</span></span>

<span data-ttu-id="2e570-170">`strUser` no puede ser una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="2e570-170">`strUser` cannot be an empty string.</span></span> <span data-ttu-id="2e570-171">Si se especifica el dominio en `strAuthority`, no también debe incluirse en `strUser`, o la función devuelve `WBEM_E_INVALID_PARAMETER`.</span><span class="sxs-lookup"><span data-stu-id="2e570-171">If the domain is specified in `strAuthority`, it must not also be included in `strUser`, or the function returns `WBEM_E_INVALID_PARAMETER`.</span></span>


## <a name="requirements"></a><span data-ttu-id="2e570-172">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2e570-172">Requirements</span></span>  
 <span data-ttu-id="2e570-173">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e570-173">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e570-174">**Encabezado:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="2e570-174">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="2e570-175">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="2e570-175">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e570-176">Vea también</span><span class="sxs-lookup"><span data-stu-id="2e570-176">See also</span></span>  
[<span data-ttu-id="2e570-177">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="2e570-177">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
