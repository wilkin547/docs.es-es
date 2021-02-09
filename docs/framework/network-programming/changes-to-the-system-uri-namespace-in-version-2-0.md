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
# <a name="changes-to-the-systemuri-namespace-in-version-20"></a>Cambios realizados en el espacio de nombres System.Uri de la versión 2.0

Se han realizado varios cambios en la clase <xref:System.Uri?displayProperty=nameWithType>. Estos cambios han corregido un comportamiento incorrecto, han mejorado el uso y también la seguridad.

## <a name="obsolete-and-deprecated-members"></a>Miembros obsoletos y en desuso

 Constructores:

- Todos los constructores que tienen un parámetro `dontEscape`.

 Métodos:

- <xref:System.Uri.CheckSecurity%2A>

- <xref:System.Uri.Escape%2A>

- <xref:System.Uri.Canonicalize%2A>

- <xref:System.Uri.Parse%2A>

- <xref:System.Uri.IsReservedCharacter%2A>

- <xref:System.Uri.IsBadFileSystemCharacter%2A>

- <xref:System.Uri.IsExcludedCharacter%2A>

- <xref:System.Uri.EscapeString%2A>

## <a name="changes"></a>Cambios

- En los esquemas URI que se sabe que no tienen un elemento de consulta (archivo, ftp y otros), el carácter "?" siempre tiene escape y no se considera el principio de un elemento <xref:System.Uri.Query%2A>.

- En el caso de los URI de archivo implícitos (con formato `c:\directory\file@name.txt`), el carácter de fragmento ("#") siempre tiene escape a menos que se solicite no escape completo o <xref:System.Uri.LocalPath%2A> sea `true`.

- Se ha quitado la compatibilidad de nombre de host UNC; se ha adoptado la especificación de IDN para representar nombres de host internacionales.

- <xref:System.Uri.LocalPath%2A> siempre devuelve una cadena totalmente sin escape.

- <xref:System.Uri.ToString%2A> no quita el escape de un carácter "%", "?" o "#" con escape.

- <xref:System.Uri.Equals%2A> ahora incluye el elemento <xref:System.Uri.Query%2A> en la comparación de igualdad.

- Los operadores "==" y "!=" se han reemplazado y vinculado al método <xref:System.Uri.Equals%2A>.

- <xref:System.Uri.IsLoopback%2A> ahora genera resultados coherentes.

- El URI "`file:///path`" ya no se traduce en `file://path`.

- "#" ahora se reconoce como un terminador de nombre de host. Es decir, `http://contoso.com#fragment` ahora se convierte en `http://contoso.com/#fragment`.

- Se ha corregido un error al combinar un URI base con un fragmento.

- Se ha corregido un error en <xref:System.Uri.HostNameType%2A>.

- Se ha corregido un error en el análisis de NNTP.

- Un URI con formato HTTP:contoso.com ahora produce una excepción de análisis.

- El marco de trabajo administra correctamente la información de usuario de un URI.

- Se ha corregido la compresión de la ruta de acceso URI para que un URI roto no pueda recorrer el sistema de archivos por encima de la raíz.

## <a name="see-also"></a>Vea también

- <xref:System.Uri?displayProperty=nameWithType>
