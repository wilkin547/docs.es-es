---
title: "Seguridad y campos de matriz públicos de sólo lectura"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: security [.NET Framework], public read-only array fields
ms.assetid: 3df28dee-2a9f-40ff-9852-bfdbe59c27f3
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d86d054d3a5a4e10b8efcc3292f3a18ea37f9b87
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="security-and-public-read-only-array-fields"></a>Seguridad y campos de matriz públicos de sólo lectura
Nunca use campos de matriz públicos de sólo lectura de bibliotecas administradas para definir el comportamiento de límite o la seguridad de las aplicaciones porque se pueden modificar los campos de matriz públicos de sólo lectura.  
  
## <a name="remarks"></a>Comentarios  
 Algunas clases de .NET framework incluyen campos públicos de sólo lectura que contienen parámetros de límite específicos de la plataforma.  Por ejemplo, el <xref:System.IO.Path.InvalidPathChars> campo es una matriz que describe los caracteres que no se permiten en una cadena de ruta de acceso de archivo.  Existen muchos campos similares a lo largo de .NET Framework.  
  
 Al igual que los valores de los campos públicos de sólo lectura <xref:System.IO.Path.InvalidPathChars> pueden modificarse mediante el código o el código que comparte el dominio de aplicación de su código.  No se deben usar campos de matriz públicos de sólo lectura similar al siguiente para definir el comportamiento del límite de las aplicaciones.  Si lo hace, código malintencionado puede modificar las definiciones de límite y usar el código de manera inesperada.  
  
 En la versión 2.0 y versiones posteriores de .NET Framework, debe utilizar métodos que devuelven una nueva matriz en lugar de usar campos de matriz públicos.  Por ejemplo, en lugar de utilizar el <xref:System.IO.Path.InvalidPathChars> campo, debe usar el <xref:System.IO.Path.GetInvalidPathChars%2A> método.  
  
 Tenga en cuenta que los tipos de .NET Framework no utilizan los campos públicos para definir tipos de límites internamente.  En su lugar, .NET Framework utiliza campos privados separados.  Cambiar los valores de estos campos públicos no altera el comportamiento de los tipos de .NET Framework.  
  
## <a name="see-also"></a>Vea también  
 [Instrucciones de codificación segura](../../../docs/standard/security/secure-coding-guidelines.md)
