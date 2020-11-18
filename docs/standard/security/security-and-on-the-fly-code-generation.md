---
title: Seguridad y generación de código inmediata
description: La generación de código en nombre del código de menor confianza que se ejecuta en una confianza mayor es un problema de seguridad, sobre todo cuando un llamador puede influir en la generación de código.
ms.date: 07/15/2020
helpviewer_keywords:
- code security, on-the-fly code generation
- on-the-fly code generation
- security [.NET], on-the-fly code generation
- secure coding, on-the-fly code generation
ms.assetid: 6d221724-bb21-4d76-90c3-0ee2a2e69be2
ms.openlocfilehash: c94da31f464a5272dd3f3c9f767a40ba7ad88a47
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94824153"
---
# <a name="security-and-on-the-fly-code-generation"></a>Seguridad y generación de código inmediata

Algunas bibliotecas funcionan generando código y ejecutándolo para realizar algunas operaciones para el llamador. El problema fundamental es generar código en nombre de código de menor confianza y ejecutarlo con una confianza superior. El problema empeora cuando el llamador puede influir en la generación de código, por lo que debe asegurarse de generar solo código que considere seguro.  
  
Necesitará saber exactamente qué código genera en todo momento. Esto significa que debe tener controles estrictos sobre los valores que obtiene de un usuario, ya sean cadenas entre comillas (que se deben escribir entre caracteres de escape para que no puedan incluir elementos de código imprevistos), identificadores (que se deben comprobar para verificar que son identificadores válidos), o cualquier otra cosa. Los identificadores pueden ser peligrosos porque un ensamblado compilado puede modificarse para que sus identificadores contengan caracteres extraños que probablemente lo interrumpirán (aunque esta es una vulnerabilidad de seguridad muy poco frecuente).  
  
Es conveniente generar código con emisión de la reflexión porque suele ayudar a evitar muchos de estos problemas.  
  
Al compilar el código, tenga en cuenta si hay alguna manera de que un programa malintencionado lo modifique. ¿Existe algún momento, por breve que sea, durante el cual un código malintencionado puede cambiar el código fuente en el disco antes de que el compilador lo lea o antes de que el código cargue el archivo .dll? Si es así, debe proteger el directorio que contiene estos archivos usando una lista de control de acceso en el sistema de archivos, según corresponda.  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de codificación segura](secure-coding-guidelines.md)
- [Seguridad de ASP.NET Core](/aspnet/core/security/)
