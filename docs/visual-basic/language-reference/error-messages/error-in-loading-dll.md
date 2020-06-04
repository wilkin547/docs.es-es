---
title: Error al cargar DLL
ms.date: 07/20/2015
f1_keywords:
- vbrID48
ms.assetid: 4226cd1f-028c-477d-88a5-cb57f7e0cdc8
ms.openlocfilehash: fd2e425f2dd3f4127cd777d4a1f7ab9809de9d45
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409637"
---
# <a name="error-in-loading-dll-visual-basic"></a><span data-ttu-id="7be4c-102">Error al cargar la biblioteca DLL (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7be4c-102">Error in loading DLL (Visual Basic)</span></span>
<span data-ttu-id="7be4c-103">Una biblioteca de vínculos dinámicos (DLL) es una biblioteca especificada en la `Lib` cláusula de una `Declare` instrucción.</span><span class="sxs-lookup"><span data-stu-id="7be4c-103">A dynamic-link library (DLL) is a library specified in the `Lib` clause of a `Declare` statement.</span></span> <span data-ttu-id="7be4c-104">Entre las posibles causas de este error se incluyen:</span><span class="sxs-lookup"><span data-stu-id="7be4c-104">Possible causes for this error include:</span></span>  
  
- <span data-ttu-id="7be4c-105">El archivo no es un ejecutable DLL.</span><span class="sxs-lookup"><span data-stu-id="7be4c-105">The file is not DLL executable.</span></span>  
  
- <span data-ttu-id="7be4c-106">El archivo no es una DLL de Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="7be4c-106">The file is not a Microsoft Windows DLL.</span></span>  
  
- <span data-ttu-id="7be4c-107">El archivo DLL hace referencia a otro archivo DLL que no está presente.</span><span class="sxs-lookup"><span data-stu-id="7be4c-107">The DLL references another DLL that is not present.</span></span>  
  
- <span data-ttu-id="7be4c-108">El archivo dll o el archivo DLL al que se hace referencia no se encuentra en un directorio especificado en la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="7be4c-108">The DLL or referenced DLL is not in a directory specified in the path.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7be4c-109">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="7be4c-109">To correct this error</span></span>  
  
- <span data-ttu-id="7be4c-110">Si el archivo es un archivo de texto de origen y, por lo tanto, no es un ejecutable DLL, se debe compilar y vincular a un formulario ejecutable DLL.</span><span class="sxs-lookup"><span data-stu-id="7be4c-110">If the file is a source-text file and therefore not DLL executable, it must be compiled and linked to a DLL-executable form.</span></span>  
  
- <span data-ttu-id="7be4c-111">Si el archivo no es una DLL de Microsoft Windows, obtenga el equivalente de Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="7be4c-111">If the file is not a Microsoft Windows DLL, obtain the Microsoft Windows equivalent.</span></span>  
  
- <span data-ttu-id="7be4c-112">Si el archivo DLL hace referencia a otro archivo DLL que no está presente, obtenga el archivo DLL al que se hace referencia y haga que esté disponible.</span><span class="sxs-lookup"><span data-stu-id="7be4c-112">If the DLL references another DLL that is not present, obtain the referenced DLL and make it available.</span></span>  
  
- <span data-ttu-id="7be4c-113">Si el archivo dll o el archivo DLL al que se hace referencia no se encuentra en un directorio especificado por la ruta de acceso, mueva el archivo DLL a un directorio al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="7be4c-113">If the DLL or referenced DLL is not in a directory specified by the path, move the DLL to a referenced directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7be4c-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7be4c-114">See also</span></span>

- [<span data-ttu-id="7be4c-115">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="7be4c-115">Declare Statement</span></span>](../statements/declare-statement.md)
