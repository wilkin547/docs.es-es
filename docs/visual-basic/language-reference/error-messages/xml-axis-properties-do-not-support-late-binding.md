---
title: Las propiedades del eje XML no admiten enlace en tiempo de ejecución
ms.date: 07/20/2015
f1_keywords:
- bc31168
- vbc31168
helpviewer_keywords:
- BC31168
ms.assetid: 45707363-55e4-4151-892d-d8729106355b
ms.openlocfilehash: 9eef245d6f83770ce26bc9e753711543241d57fb
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163290"
---
# <a name="bc31168-xml-axis-properties-do-not-support-late-binding"></a><span data-ttu-id="a0e85-102">BC31168: las propiedades del eje XML no admiten enlace en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="a0e85-102">BC31168: XML axis properties do not support late binding</span></span>

<span data-ttu-id="a0e85-103">Se ha hecho referencia a una propiedad de eje XML para un objeto sin tipo.</span><span class="sxs-lookup"><span data-stu-id="a0e85-103">An XML axis property has been referenced for an untyped object.</span></span>

 <span data-ttu-id="a0e85-104">**Identificador de error:** BC31168</span><span class="sxs-lookup"><span data-stu-id="a0e85-104">**Error ID:** BC31168</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="a0e85-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="a0e85-105">To correct this error</span></span>

- <span data-ttu-id="a0e85-106">Asegúrese de que el objeto es un objeto fuertemente tipado <xref:System.Xml.Linq.XElement> antes de hacer referencia a la propiedad de eje XML.</span><span class="sxs-lookup"><span data-stu-id="a0e85-106">Ensure that the object is a strong-typed <xref:System.Xml.Linq.XElement> object before referencing the XML axis property.</span></span>

## <a name="see-also"></a><span data-ttu-id="a0e85-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="a0e85-107">See also</span></span>

- [<span data-ttu-id="a0e85-108">Propiedades de eje XML</span><span class="sxs-lookup"><span data-stu-id="a0e85-108">XML Axis Properties</span></span>](../xml-axis/index.md)
- [<span data-ttu-id="a0e85-109">XML</span><span class="sxs-lookup"><span data-stu-id="a0e85-109">XML</span></span>](../../programming-guide/language-features/xml/index.md)
