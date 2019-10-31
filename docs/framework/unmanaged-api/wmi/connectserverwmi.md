---
title: Función ConnectServerWmi (referencia de la API no administrada)
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
ms.openlocfilehash: 25a73060ed242fd0e77042cd0ea9618b9b27250f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128690"
---
# <a name="connectserverwmi-function"></a><span data-ttu-id="bf9d5-103">ConnectServerWmi función)</span><span class="sxs-lookup"><span data-stu-id="bf9d5-103">ConnectServerWmi function</span></span>

<span data-ttu-id="bf9d5-104">Crea una conexión a un espacio de nombres de WMI a través de DCOM en un equipo especificado.</span><span class="sxs-lookup"><span data-stu-id="bf9d5-104">Creates a connection through DCOM to a WMI namespace on a specified computer.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="bf9d5-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bf9d5-105">Syntax</span></span>

```cpp
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

## <a name="parameters"></a><span data-ttu-id="bf9d5-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bf9d5-106">Parameters</span></span>

`strNetworkResource`\
<span data-ttu-id="bf9d5-107">de Puntero a una `BSTR` válida que contiene la ruta de acceso del objeto del espacio de nombres WMI correcto.</span><span class="sxs-lookup"><span data-stu-id="bf9d5-107">[in] Pointer to a valid `BSTR` that contains the object path of the correct WMI namespace.</span></span> <span data-ttu-id="bf9d5-108">Vea la sección [comentarios](#remarks) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="bf9d5-108">See the [Remarks](#remarks) section for more information.</span></span>

`strUser`\
<span data-ttu-id="bf9d5-109">de Puntero a una `BSTR` válida que contiene el nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="bf9d5-109">[in] A pointer to a valid `BSTR` that contains the user name.</span></span> <span data-ttu-id="bf9d5-110">Un valor `null` indica el contexto de seguridad actual.</span><span class="sxs-lookup"><span data-stu-id="bf9d5-110">A `null` value indicates the current security context.</span></span> <span data-ttu-id="bf9d5-111">Si el usuario es de un dominio diferente del actual, `strUser` también puede contener el dominio y el nombre de usuario separados por una barra diagonal inversa.</span><span class="sxs-lookup"><span data-stu-id="bf9d5-111">If the user is from a different domain than the current one, `strUser` can also contain the domain and user name separated by a backslash.</span></span> <span data-ttu-id="bf9d5-112">`strUser` también pueden tener el formato de nombre principal de usuario (UPN), como `userName@domainName`.</span><span class="sxs-lookup"><span data-stu-id="bf9d5-112">`strUser` can also be in user principal name (UPN) format, such as `userName@domainName`.</span></span> <span data-ttu-id="bf9d5-113">Vea la sección [comentarios](#remarks) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="bf9d5-113">See the [Remarks](#remarks) section for more information.</span></span>

`strPassword`\
<span data-ttu-id="bf9d5-114">de Puntero a un `BSTR` válido que contiene la contraseña.</span><span class="sxs-lookup"><span data-stu-id="bf9d5-114">[in] A pointer to a valid `BSTR` that contains the password.</span></span> <span data-ttu-id="bf9d5-115">`null` indica el contexto de seguridad actual.</span><span class="sxs-lookup"><span data-stu-id="bf9d5-115">A `null` indicates the current security context.</span></span> <span data-ttu-id="bf9d5-116">Una cadena vacía ("") indica una contraseña de longitud cero válida.</span><span class="sxs-lookup"><span data-stu-id="bf9d5-116">An empty string ("") indicates a valid zero-length password.</span></span>

`strLocale`\
<span data-ttu-id="bf9d5-117">de Puntero a un `BSTR` válido que indica la configuración regional correcta para la recuperación de información.</span><span class="sxs-lookup"><span data-stu-id="bf9d5-117">[in] A pointer to a valid `BSTR` that indicates the correct locale for information retrieval.</span></span> <span data-ttu-id="bf9d5-118">En el caso de los identificadores de configuración regional de Microsoft, el formato de la cadena es "MS\_*XXX*", donde *XXX* es una cadena en formato hexadecimal que indica el identificador de configuración regional (LCID).</span><span class="sxs-lookup"><span data-stu-id="bf9d5-118">For Microsoft locale identifiers, the format of the string is "MS\_*xxx*", where *xxx* is a string in hexadecimal form that indicates the locale identifier (LCID).</span></span> <span data-ttu-id="bf9d5-119">Si se especifica una configuración regional no válida, el método devuelve `WBEM_E_INVALID_PARAMETER` excepto en Windows 7, donde se usa en su lugar la configuración regional predeterminada del servidor.</span><span class="sxs-lookup"><span data-stu-id="bf9d5-119">If an invalid locale is specified, the method returns `WBEM_E_INVALID_PARAMETER` except on Windows 7, where the default locale of the server is used instead.</span></span> <span data-ttu-id="bf9d5-120">Si es "null1", se usa la configuración regional actual.</span><span class="sxs-lookup"><span data-stu-id="bf9d5-120">If \`null1, the current locale is used.</span></span>

`lSecurityFlags`\
<span data-ttu-id="bf9d5-121">de Marcas que se van a pasar al método `ConnectServerWmi`.</span><span class="sxs-lookup"><span data-stu-id="bf9d5-121">[in] Flags to pass to the `ConnectServerWmi` method.</span></span> <span data-ttu-id="bf9d5-122">Un valor de cero (0) para este parámetro hace que la llamada a `ConnectServerWmi` devuelva solo después de establecer una conexión con el servidor.</span><span class="sxs-lookup"><span data-stu-id="bf9d5-122">A value of zero (0) for this parameter results in the call to `ConnectServerWmi` returning only after a connection to the server is established.</span></span> <span data-ttu-id="bf9d5-123">Esto podría dar lugar a que una aplicación no responda indefinidamente si el servidor está dañado.</span><span class="sxs-lookup"><span data-stu-id="bf9d5-123">This could result in an application not responding indefinitely if the server is broken.</span></span> <span data-ttu-id="bf9d5-124">Los otros valores válidos son:</span><span class="sxs-lookup"><span data-stu-id="bf9d5-124">The other valid values are:</span></span>

| <span data-ttu-id="bf9d5-125">Constante</span><span class="sxs-lookup"><span data-stu-id="bf9d5-125">Constant</span></span>  | <span data-ttu-id="bf9d5-126">Valor</span><span class="sxs-lookup"><span data-stu-id="bf9d5-126">Value</span></span>  | <span data-ttu-id="bf9d5-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="bf9d5-127">Description</span></span>  |
|---------|---------|---------|
| `CONNECT_REPOSITORY_ONLY` | <span data-ttu-id="bf9d5-128">0x40</span><span class="sxs-lookup"><span data-stu-id="bf9d5-128">0x40</span></span> | <span data-ttu-id="bf9d5-129">Reservado para uso interno.</span><span class="sxs-lookup"><span data-stu-id="bf9d5-129">Reserved for internal use.</span></span> <span data-ttu-id="bf9d5-130">No utilizar.</span><span class="sxs-lookup"><span data-stu-id="bf9d5-130">Do not use.</span></span> |
| `WBEM_FLAG_CONNECT_USE_MAX_WAIT` | <span data-ttu-id="bf9d5-131">0x80</span><span class="sxs-lookup"><span data-stu-id="bf9d5-131">0x80</span></span> | <span data-ttu-id="bf9d5-132">`ConnectServerWmi` devuelve en dos minutos o menos.</span><span class="sxs-lookup"><span data-stu-id="bf9d5-132">`ConnectServerWmi` returns in two minutes or less.</span></span> |

`strAuthority`\
<span data-ttu-id="bf9d5-133">de El nombre de dominio del usuario.</span><span class="sxs-lookup"><span data-stu-id="bf9d5-133">[in] The domain name of the user.</span></span> <span data-ttu-id="bf9d5-134">Puede tener los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="bf9d5-134">It can have the following values:</span></span>

| <span data-ttu-id="bf9d5-135">Valor</span><span class="sxs-lookup"><span data-stu-id="bf9d5-135">Value</span></span> | <span data-ttu-id="bf9d5-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="bf9d5-136">Description</span></span> |
|---------|---------|
| <span data-ttu-id="bf9d5-137">En blanco</span><span class="sxs-lookup"><span data-stu-id="bf9d5-137">blank</span></span> | <span data-ttu-id="bf9d5-138">Se usa la autenticación NTLM y se usa el dominio NTLM del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="bf9d5-138">NTLM authentication is used, and the NTLM domain of the current user is used.</span></span> <span data-ttu-id="bf9d5-139">Si `strUser` especifica el dominio (la ubicación recomendada), no debe especificarse aquí.</span><span class="sxs-lookup"><span data-stu-id="bf9d5-139">If `strUser` specifies the domain (the recommended location), it must not be specified here.</span></span> <span data-ttu-id="bf9d5-140">La función devuelve `WBEM_E_INVALID_PARAMETER` si se especifica el dominio en ambos parámetros.</span><span class="sxs-lookup"><span data-stu-id="bf9d5-140">The function returns `WBEM_E_INVALID_PARAMETER` if you specify the domain in both parameters.</span></span> |
| <span data-ttu-id="bf9d5-141">Kerberos:*nombre principal*</span><span class="sxs-lookup"><span data-stu-id="bf9d5-141">Kerberos:*principal name*</span></span> | <span data-ttu-id="bf9d5-142">Se usa la autenticación Kerberos y este parámetro contiene un nombre de entidad de seguridad Kerberos.</span><span class="sxs-lookup"><span data-stu-id="bf9d5-142">Kerberos authentication is used, and this parameter contains a Kerberos principal name.</span></span> |
| <span data-ttu-id="bf9d5-143">NTLMDOMAIN:*nombre de dominio*</span><span class="sxs-lookup"><span data-stu-id="bf9d5-143">NTLMDOMAIN:*domain name*</span></span> | <span data-ttu-id="bf9d5-144">Se usa la autenticación NT LAN Manager y este parámetro contiene un nombre de dominio NTLM.</span><span class="sxs-lookup"><span data-stu-id="bf9d5-144">NT LAN Manager authentication is used, and this parameter contains an NTLM domain name.</span></span> |

`pCtx`\
<span data-ttu-id="bf9d5-145">de Normalmente, este parámetro es `null`.</span><span class="sxs-lookup"><span data-stu-id="bf9d5-145">[in] Typically, this parameter is `null`.</span></span> <span data-ttu-id="bf9d5-146">De lo contrario, es un puntero a un objeto [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) requerido por uno o más proveedores de clases dinámicas.</span><span class="sxs-lookup"><span data-stu-id="bf9d5-146">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) object required by one or more dynamic class providers.</span></span>

`ppNamespace`\
<span data-ttu-id="bf9d5-147">enuncia Cuando la función devuelve, recibe un puntero a un objeto [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) enlazado al espacio de nombres especificado.</span><span class="sxs-lookup"><span data-stu-id="bf9d5-147">[out] When the function returns, receives a pointer to an [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object bound to the specified namespace.</span></span> <span data-ttu-id="bf9d5-148">Está configurado para apuntar a `null` cuando se produce un error.</span><span class="sxs-lookup"><span data-stu-id="bf9d5-148">It is set to point to `null` when there is an error.</span></span>

`impLevel`\
<span data-ttu-id="bf9d5-149">de Nivel de suplantación.</span><span class="sxs-lookup"><span data-stu-id="bf9d5-149">[in] The impersonation level.</span></span>

`authLevel`\
<span data-ttu-id="bf9d5-150">de Nivel de autorización.</span><span class="sxs-lookup"><span data-stu-id="bf9d5-150">[in] The authorization level.</span></span>

## <a name="return-value"></a><span data-ttu-id="bf9d5-151">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="bf9d5-151">Return value</span></span>

<span data-ttu-id="bf9d5-152">Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="bf9d5-152">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="bf9d5-153">Constante</span><span class="sxs-lookup"><span data-stu-id="bf9d5-153">Constant</span></span>  |<span data-ttu-id="bf9d5-154">Valor</span><span class="sxs-lookup"><span data-stu-id="bf9d5-154">Value</span></span>  |<span data-ttu-id="bf9d5-155">Descripción</span><span class="sxs-lookup"><span data-stu-id="bf9d5-155">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="bf9d5-156">0x80041001</span><span class="sxs-lookup"><span data-stu-id="bf9d5-156">0x80041001</span></span> | <span data-ttu-id="bf9d5-157">Se ha producido un error general.</span><span class="sxs-lookup"><span data-stu-id="bf9d5-157">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="bf9d5-158">0x80041008</span><span class="sxs-lookup"><span data-stu-id="bf9d5-158">0x80041008</span></span> | <span data-ttu-id="bf9d5-159">Un parámetro no es válido.</span><span class="sxs-lookup"><span data-stu-id="bf9d5-159">A parameter is not valid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="bf9d5-160">0x80041006</span><span class="sxs-lookup"><span data-stu-id="bf9d5-160">0x80041006</span></span> | <span data-ttu-id="bf9d5-161">No hay suficiente memoria disponible para completar la operación.</span><span class="sxs-lookup"><span data-stu-id="bf9d5-161">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="bf9d5-162">0</span><span class="sxs-lookup"><span data-stu-id="bf9d5-162">0</span></span> | <span data-ttu-id="bf9d5-163">La llamada de función se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="bf9d5-163">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="bf9d5-164">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bf9d5-164">Remarks</span></span>

<span data-ttu-id="bf9d5-165">Esta función contiene una llamada al método [IWbemLocator:: ConnectServer](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemlocator-connectserver) .</span><span class="sxs-lookup"><span data-stu-id="bf9d5-165">This function wraps a call to the [IWbemLocator::ConnectServer](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemlocator-connectserver) method.</span></span>

<span data-ttu-id="bf9d5-166">Para el acceso local al espacio de nombres predeterminado, `strNetworkResource` puede ser una ruta de acceso de objeto simple: "root\default" o "\\.\root\default".</span><span class="sxs-lookup"><span data-stu-id="bf9d5-166">For local access to the default namespace, `strNetworkResource` can be a simple object path: "root\default" or "\\.\root\default".</span></span> <span data-ttu-id="bf9d5-167">Para obtener acceso al espacio de nombres predeterminado de un equipo remoto mediante COM o redes compatibles con Microsoft, incluya el nombre del equipo: "\\myserver\root\default".</span><span class="sxs-lookup"><span data-stu-id="bf9d5-167">For access to the default namespace on a remote computer using COM or Microsoft-compatible networking, include the computer name: "\\myserver\root\default".</span></span> <span data-ttu-id="bf9d5-168">El nombre del equipo también puede ser un nombre DNS o una dirección IP.</span><span class="sxs-lookup"><span data-stu-id="bf9d5-168">The computer name also can be a DNS name or IP address.</span></span> <span data-ttu-id="bf9d5-169">La función `ConnectServerWmi` también puede conectarse con equipos que ejecutan IPv6 mediante una dirección IPv6.</span><span class="sxs-lookup"><span data-stu-id="bf9d5-169">The `ConnectServerWmi` function can also connect with computers running IPv6 using an IPv6 address.</span></span>

<span data-ttu-id="bf9d5-170">`strUser` no puede ser una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="bf9d5-170">`strUser` cannot be an empty string.</span></span> <span data-ttu-id="bf9d5-171">Si el dominio se especifica en `strAuthority`, no se debe incluir también en `strUser`o la función devuelve `WBEM_E_INVALID_PARAMETER`.</span><span class="sxs-lookup"><span data-stu-id="bf9d5-171">If the domain is specified in `strAuthority`, it must not also be included in `strUser`, or the function returns `WBEM_E_INVALID_PARAMETER`.</span></span>

## <a name="requirements"></a><span data-ttu-id="bf9d5-172">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bf9d5-172">Requirements</span></span>

 <span data-ttu-id="bf9d5-173">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf9d5-173">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="bf9d5-174">**Encabezado:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="bf9d5-174">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="bf9d5-175">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="bf9d5-175">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="bf9d5-176">Vea también</span><span class="sxs-lookup"><span data-stu-id="bf9d5-176">See also</span></span>

- [<span data-ttu-id="bf9d5-177">WMI y contadores de rendimiento (referencia de la API no administrada)</span><span class="sxs-lookup"><span data-stu-id="bf9d5-177">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
