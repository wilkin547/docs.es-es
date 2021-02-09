---
description: 'Más información acerca de: Cambios realizados en el espacio de nombres System.Uri de la versión 2.0'
title: Cambios realizados en el espacio de nombres System.Uri de la versión 2.0
ms.date: 03/30/2017
ms.assetid: 35883fe9-2d09-4d8b-80ca-cf23a941e459
ms.openlocfilehash: 8b5e2f2b3b59fba96e20e40a4df18273a2f6034f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791626"
---
# <a name="changes-to-the-systemuri-namespace-in-version-20"></a><span data-ttu-id="fcf55-103">Cambios realizados en el espacio de nombres System.Uri de la versión 2.0</span><span class="sxs-lookup"><span data-stu-id="fcf55-103">Changes to the System.Uri namespace in version 2.0</span></span>

<span data-ttu-id="fcf55-104">Se han realizado varios cambios en la clase <xref:System.Uri?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fcf55-104">Several changes were made to the <xref:System.Uri?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="fcf55-105">Estos cambios han corregido un comportamiento incorrecto, han mejorado el uso y también la seguridad.</span><span class="sxs-lookup"><span data-stu-id="fcf55-105">These changes fixed incorrect behavior, enhanced usability, and enhanced security.</span></span>

## <a name="obsolete-and-deprecated-members"></a><span data-ttu-id="fcf55-106">Miembros obsoletos y en desuso</span><span class="sxs-lookup"><span data-stu-id="fcf55-106">Obsolete and deprecated Members</span></span>

 <span data-ttu-id="fcf55-107">Constructores:</span><span class="sxs-lookup"><span data-stu-id="fcf55-107">Constructors:</span></span>

- <span data-ttu-id="fcf55-108">Todos los constructores que tienen un parámetro `dontEscape`.</span><span class="sxs-lookup"><span data-stu-id="fcf55-108">All constructors that have a `dontEscape` parameter.</span></span>

 <span data-ttu-id="fcf55-109">Métodos:</span><span class="sxs-lookup"><span data-stu-id="fcf55-109">Methods:</span></span>

- <xref:System.Uri.CheckSecurity%2A>

- <xref:System.Uri.Escape%2A>

- <xref:System.Uri.Canonicalize%2A>

- <xref:System.Uri.Parse%2A>

- <xref:System.Uri.IsReservedCharacter%2A>

- <xref:System.Uri.IsBadFileSystemCharacter%2A>

- <xref:System.Uri.IsExcludedCharacter%2A>

- <xref:System.Uri.EscapeString%2A>

## <a name="changes"></a><span data-ttu-id="fcf55-110">Cambios</span><span class="sxs-lookup"><span data-stu-id="fcf55-110">Changes</span></span>

- <span data-ttu-id="fcf55-111">En los esquemas URI que se sabe que no tienen un elemento de consulta (archivo, ftp y otros), el carácter "?" siempre tiene escape y no se considera el principio de un elemento <xref:System.Uri.Query%2A>.</span><span class="sxs-lookup"><span data-stu-id="fcf55-111">For URI schemes that are known to not have a query part (file, ftp, and others), the '?' character is always escaped and is not considered the beginning of a <xref:System.Uri.Query%2A> part.</span></span>

- <span data-ttu-id="fcf55-112">En el caso de los URI de archivo implícitos (con formato `c:\directory\file@name.txt`), el carácter de fragmento ("#") siempre tiene escape a menos que se solicite no escape completo o <xref:System.Uri.LocalPath%2A> sea `true`.</span><span class="sxs-lookup"><span data-stu-id="fcf55-112">For implicit file URIs (of the form `c:\directory\file@name.txt`), the fragment character ('#') is always escaped unless full unescaping is requested or <xref:System.Uri.LocalPath%2A> is `true`.</span></span>

- <span data-ttu-id="fcf55-113">Se ha quitado la compatibilidad de nombre de host UNC; se ha adoptado la especificación de IDN para representar nombres de host internacionales.</span><span class="sxs-lookup"><span data-stu-id="fcf55-113">UNC hostname support was removed; the IDN specification for representing international hostnames was adopted.</span></span>

- <span data-ttu-id="fcf55-114"><xref:System.Uri.LocalPath%2A> siempre devuelve una cadena totalmente sin escape.</span><span class="sxs-lookup"><span data-stu-id="fcf55-114"><xref:System.Uri.LocalPath%2A> always returns a completely unescaped string.</span></span>

- <span data-ttu-id="fcf55-115"><xref:System.Uri.ToString%2A> no quita el escape de un carácter "%", "?" o "#" con escape.</span><span class="sxs-lookup"><span data-stu-id="fcf55-115"><xref:System.Uri.ToString%2A> does not unescape an escaped '%', '?', or '#' character.</span></span>

- <span data-ttu-id="fcf55-116"><xref:System.Uri.Equals%2A> ahora incluye el elemento <xref:System.Uri.Query%2A> en la comparación de igualdad.</span><span class="sxs-lookup"><span data-stu-id="fcf55-116"><xref:System.Uri.Equals%2A> now includes the <xref:System.Uri.Query%2A> part in the equality check.</span></span>

- <span data-ttu-id="fcf55-117">Los operadores "==" y "!=" se han reemplazado y vinculado al método <xref:System.Uri.Equals%2A>.</span><span class="sxs-lookup"><span data-stu-id="fcf55-117">Operators "==" and "!=" are overridden and linked to the <xref:System.Uri.Equals%2A> method.</span></span>

- <span data-ttu-id="fcf55-118"><xref:System.Uri.IsLoopback%2A> ahora genera resultados coherentes.</span><span class="sxs-lookup"><span data-stu-id="fcf55-118"><xref:System.Uri.IsLoopback%2A> now produces consistent results.</span></span>

- <span data-ttu-id="fcf55-119">El URI "`file:///path`" ya no se traduce en `file://path`.</span><span class="sxs-lookup"><span data-stu-id="fcf55-119">The URI "`file:///path`" is no longer translated into `file://path`.</span></span>

- <span data-ttu-id="fcf55-120">"#" ahora se reconoce como un terminador de nombre de host.</span><span class="sxs-lookup"><span data-stu-id="fcf55-120">"#" is now recognized as a host name terminator.</span></span> <span data-ttu-id="fcf55-121">Es decir, `http://contoso.com#fragment` ahora se convierte en `http://contoso.com/#fragment`.</span><span class="sxs-lookup"><span data-stu-id="fcf55-121">That is, `http://contoso.com#fragment` is now converted to `http://contoso.com/#fragment`.</span></span>

- <span data-ttu-id="fcf55-122">Se ha corregido un error al combinar un URI base con un fragmento.</span><span class="sxs-lookup"><span data-stu-id="fcf55-122">A bug when combining a base URI with a fragment has been fixed.</span></span>

- <span data-ttu-id="fcf55-123">Se ha corregido un error en <xref:System.Uri.HostNameType%2A>.</span><span class="sxs-lookup"><span data-stu-id="fcf55-123">A bug in <xref:System.Uri.HostNameType%2A> is fixed.</span></span>

- <span data-ttu-id="fcf55-124">Se ha corregido un error en el análisis de NNTP.</span><span class="sxs-lookup"><span data-stu-id="fcf55-124">A bug in NNTP parsing is fixed.</span></span>

- <span data-ttu-id="fcf55-125">Un URI con formato HTTP:contoso.com ahora produce una excepción de análisis.</span><span class="sxs-lookup"><span data-stu-id="fcf55-125">A URI of the form HTTP:contoso.com now throws a parsing exception.</span></span>

- <span data-ttu-id="fcf55-126">El marco de trabajo administra correctamente la información de usuario de un URI.</span><span class="sxs-lookup"><span data-stu-id="fcf55-126">The Framework correctly handles userinfo in a URI.</span></span>

- <span data-ttu-id="fcf55-127">Se ha corregido la compresión de la ruta de acceso URI para que un URI roto no pueda recorrer el sistema de archivos por encima de la raíz.</span><span class="sxs-lookup"><span data-stu-id="fcf55-127">URI path compression is fixed so that a broken URI cannot traverse the file system above the root.</span></span>

## <a name="see-also"></a><span data-ttu-id="fcf55-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="fcf55-128">See also</span></span>

- <xref:System.Uri?displayProperty=nameWithType>
