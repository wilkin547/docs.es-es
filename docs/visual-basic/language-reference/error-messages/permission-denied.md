---
title: Permiso denegado (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrID70
ms.assetid: 71f46756-f522-4814-aab4-492bf9924245
ms.openlocfilehash: ad75c556748bf5c0f9cef55310c4ffa7b01fd458
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59318837"
---
# <a name="permission-denied-visual-basic"></a><span data-ttu-id="11162-102">Permiso denegado (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="11162-102">Permission denied (Visual Basic)</span></span>
<span data-ttu-id="11162-103">Se ha intentado escribir en un disco protegido contra escritura o tener acceso a un archivo bloqueado.</span><span class="sxs-lookup"><span data-stu-id="11162-103">An attempt was made to write to a write-protected disk or to access a locked file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="11162-104">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="11162-104">To correct this error</span></span>  
  
1. <span data-ttu-id="11162-105">Para abrir un archivo protegido contra escritura, cambie el atributo de protección contra escritura del archivo.</span><span class="sxs-lookup"><span data-stu-id="11162-105">To open a write-protected file, change the write-protection attribute of the file.</span></span>  
  
2. <span data-ttu-id="11162-106">Asegúrese de que otro proceso no ha bloqueado el archivo y espere para abrir el archivo hasta que el otro proceso lo libere.</span><span class="sxs-lookup"><span data-stu-id="11162-106">Make sure that another process has not locked the file, and wait to open the file until the other process releases it.</span></span>  
  
3. <span data-ttu-id="11162-107">Para obtener acceso al registro, compruebe que los permisos de usuario incluyen este tipo de acceso al registro.</span><span class="sxs-lookup"><span data-stu-id="11162-107">To access the registry, check that your user permissions include this type of registry access.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11162-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="11162-108">See also</span></span>

- [<span data-ttu-id="11162-109">Tipos de error</span><span class="sxs-lookup"><span data-stu-id="11162-109">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
