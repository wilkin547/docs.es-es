---
title: Seguridad y generación de código inmediata
description: La generación de código en nombre del código de menor confianza que se ejecuta en una confianza mayor es un problema de seguridad, sobre todo cuando un llamador puede influir en la generación de código.
ms.date: 07/15/2020
ms.technology: dotnet-standard
helpviewer_keywords:
- code security, on-the-fly code generation
- on-the-fly code generation
- security [.NET], on-the-fly code generation
- secure coding, on-the-fly code generation
ms.assetid: 6d221724-bb21-4d76-90c3-0ee2a2e69be2
ms.openlocfilehash: a3fc51c346feffa85537d95ccdbd23d943827edf
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87555700"
---
# <a name="security-and-on-the-fly-code-generation"></a><span data-ttu-id="5fa25-103">Seguridad y generación de código inmediata</span><span class="sxs-lookup"><span data-stu-id="5fa25-103">Security and On-the-Fly Code Generation</span></span>

<span data-ttu-id="5fa25-104">Algunas bibliotecas funcionan generando código y ejecutándolo para realizar algunas operaciones para el llamador.</span><span class="sxs-lookup"><span data-stu-id="5fa25-104">Some libraries operate by generating code and running it to perform some operation for the caller.</span></span> <span data-ttu-id="5fa25-105">El problema fundamental es generar código en nombre de código de menor confianza y ejecutarlo con una confianza superior.</span><span class="sxs-lookup"><span data-stu-id="5fa25-105">The basic problem is generating code on behalf of lesser-trust code and running it at a higher trust.</span></span> <span data-ttu-id="5fa25-106">El problema empeora cuando el llamador puede influir en la generación de código, por lo que debe asegurarse de generar solo código que considere seguro.</span><span class="sxs-lookup"><span data-stu-id="5fa25-106">The problem worsens when the caller can influence code generation, so you must ensure that only code you consider safe is generated.</span></span>  
  
<span data-ttu-id="5fa25-107">Necesitará saber exactamente qué código genera en todo momento.</span><span class="sxs-lookup"><span data-stu-id="5fa25-107">You need to know exactly what code you are generating at all times.</span></span> <span data-ttu-id="5fa25-108">Esto significa que debe tener controles estrictos sobre los valores que obtiene de un usuario, ya sean cadenas entre comillas (que se deben escribir entre caracteres de escape para que no puedan incluir elementos de código imprevistos), identificadores (que se deben comprobar para verificar que son identificadores válidos), o cualquier otra cosa.</span><span class="sxs-lookup"><span data-stu-id="5fa25-108">This means that you must have strict controls on any values that you get from a user, be they quote-enclosed strings (which should be escaped so they cannot include unexpected code elements), identifiers (which should be checked to verify that they are valid identifiers), or anything else.</span></span> <span data-ttu-id="5fa25-109">Los identificadores pueden ser peligrosos porque un ensamblado compilado puede modificarse para que sus identificadores contengan caracteres extraños que probablemente lo interrumpirán (aunque esta es una vulnerabilidad de seguridad muy poco frecuente).</span><span class="sxs-lookup"><span data-stu-id="5fa25-109">Identifiers can be dangerous because a compiled assembly can be modified so that its identifiers contain strange characters, which will probably break it (although this is rarely a security vulnerability).</span></span>  
  
<span data-ttu-id="5fa25-110">Es conveniente generar código con emisión de la reflexión porque suele ayudar a evitar muchos de estos problemas.</span><span class="sxs-lookup"><span data-stu-id="5fa25-110">It is recommended that you generate code with reflection emit, which often helps you avoid many of these problems.</span></span>  
  
<span data-ttu-id="5fa25-111">Al compilar el código, tenga en cuenta si hay alguna manera de que un programa malintencionado lo modifique.</span><span class="sxs-lookup"><span data-stu-id="5fa25-111">When you compile the code, consider whether there is some way a malicious program could modify it.</span></span> <span data-ttu-id="5fa25-112">¿Existe algún momento, por breve que sea, durante el cual un código malintencionado puede cambiar el código fuente en el disco antes de que el compilador lo lea o antes de que el código cargue el archivo .dll?</span><span class="sxs-lookup"><span data-stu-id="5fa25-112">Is there a small window of time during which malicious code can change source code on disk before the compiler reads it or before your code loads the .dll file?</span></span> <span data-ttu-id="5fa25-113">Si es así, debe proteger el directorio que contiene estos archivos usando una lista de control de acceso en el sistema de archivos, según corresponda.</span><span class="sxs-lookup"><span data-stu-id="5fa25-113">If so, you must protect the directory containing these files, using an Access Control List in the file system, as appropriate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fa25-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5fa25-114">See also</span></span>

- [<span data-ttu-id="5fa25-115">Instrucciones de codificación segura</span><span class="sxs-lookup"><span data-stu-id="5fa25-115">Secure Coding Guidelines</span></span>](secure-coding-guidelines.md)
- [<span data-ttu-id="5fa25-116">Seguridad de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="5fa25-116">ASP.NET Core Security</span></span>](/aspnet/core/security/)
