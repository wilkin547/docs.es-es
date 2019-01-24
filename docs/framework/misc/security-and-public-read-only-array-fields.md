---
title: Seguridad y campos de matriz públicos de sólo lectura
ms.date: 03/30/2017
helpviewer_keywords:
- security [.NET Framework], public read-only array fields
ms.assetid: 3df28dee-2a9f-40ff-9852-bfdbe59c27f3
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 03f3ce51eaab9e08d5f05932d9360adc4fd2110f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54560998"
---
# <a name="security-and-public-read-only-array-fields"></a>Seguridad y campos de matriz públicos de sólo lectura
Nunca use los campos de matriz públicos de sólo lectura de las bibliotecas administradas para definir el comportamiento de límite o la seguridad de las aplicaciones porque se pueden modificar los campos de matriz públicos de sólo lectura.  
  
## <a name="remarks"></a>Comentarios  
 Algunas clases de .NET framework incluyen campos públicos de sólo lectura que contienen los parámetros de los límites específicos de la plataforma.  Por ejemplo, el <xref:System.IO.Path.InvalidPathChars> campo es una matriz que describe los caracteres que no se permiten en una cadena de ruta de acceso de archivo.  Existen muchos campos similares a lo largo de .NET Framework.  
  
 Al igual que los valores de campos públicos de sólo lectura <xref:System.IO.Path.InvalidPathChars> puede modificarse mediante el código o el código que comparte el dominio de aplicación de su código.  No debe usar los campos de matriz públicos de sólo lectura similar al siguiente para definir el comportamiento de límite de sus aplicaciones.  Si lo hace, código malintencionado puede modificar las definiciones de límite y usar el código de manera inesperada.  
  
 En la versión 2.0 y versiones posteriores de .NET Framework, debe usar los métodos que devuelven una nueva matriz en lugar de usar campos de matriz públicos.  Por ejemplo, en lugar de usar el <xref:System.IO.Path.InvalidPathChars> campo, debe usar el <xref:System.IO.Path.GetInvalidPathChars%2A> método.  
  
 Tenga en cuenta que los tipos de .NET Framework no utilizan los campos públicos para definir tipos de límites internamente.  En su lugar, .NET Framework utiliza campos privados separados.  Cambiar los valores de estos campos públicos no modifica el comportamiento de los tipos de .NET Framework.  
  
## <a name="see-also"></a>Vea también
- [Instrucciones de codificación segura](../../../docs/standard/security/secure-coding-guidelines.md)
