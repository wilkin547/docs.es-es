---
description: 'Más información acerca de: error al cargar el archivo DLL (Visual Basic)'
title: Error al cargar DLL
ms.date: 07/20/2015
f1_keywords:
- vbrID48
ms.assetid: 4226cd1f-028c-477d-88a5-cb57f7e0cdc8
ms.openlocfilehash: 098d05e93d328f3667000bd81290f4b77cf7949e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796514"
---
# <a name="error-in-loading-dll-visual-basic"></a><span data-ttu-id="1b08b-103">Error al cargar la biblioteca DLL (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1b08b-103">Error in loading DLL (Visual Basic)</span></span>

<span data-ttu-id="1b08b-104">Una biblioteca de vínculos dinámicos (DLL) es una biblioteca especificada en la `Lib` cláusula de una `Declare` instrucción.</span><span class="sxs-lookup"><span data-stu-id="1b08b-104">A dynamic-link library (DLL) is a library specified in the `Lib` clause of a `Declare` statement.</span></span> <span data-ttu-id="1b08b-105">Entre las posibles causas de este error se incluyen:</span><span class="sxs-lookup"><span data-stu-id="1b08b-105">Possible causes for this error include:</span></span>  
  
- <span data-ttu-id="1b08b-106">El archivo no es un ejecutable DLL.</span><span class="sxs-lookup"><span data-stu-id="1b08b-106">The file is not DLL executable.</span></span>  
  
- <span data-ttu-id="1b08b-107">El archivo no es una DLL de Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="1b08b-107">The file is not a Microsoft Windows DLL.</span></span>  
  
- <span data-ttu-id="1b08b-108">El archivo DLL hace referencia a otro archivo DLL que no está presente.</span><span class="sxs-lookup"><span data-stu-id="1b08b-108">The DLL references another DLL that is not present.</span></span>  
  
- <span data-ttu-id="1b08b-109">El archivo dll o el archivo DLL al que se hace referencia no se encuentra en un directorio especificado en la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="1b08b-109">The DLL or referenced DLL is not in a directory specified in the path.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1b08b-110">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="1b08b-110">To correct this error</span></span>  
  
- <span data-ttu-id="1b08b-111">Si el archivo es un archivo de texto de origen y, por lo tanto, no es un ejecutable DLL, se debe compilar y vincular a un formulario ejecutable DLL.</span><span class="sxs-lookup"><span data-stu-id="1b08b-111">If the file is a source-text file and therefore not DLL executable, it must be compiled and linked to a DLL-executable form.</span></span>  
  
- <span data-ttu-id="1b08b-112">Si el archivo no es una DLL de Microsoft Windows, obtenga el equivalente de Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="1b08b-112">If the file is not a Microsoft Windows DLL, obtain the Microsoft Windows equivalent.</span></span>  
  
- <span data-ttu-id="1b08b-113">Si el archivo DLL hace referencia a otro archivo DLL que no está presente, obtenga el archivo DLL al que se hace referencia y haga que esté disponible.</span><span class="sxs-lookup"><span data-stu-id="1b08b-113">If the DLL references another DLL that is not present, obtain the referenced DLL and make it available.</span></span>  
  
- <span data-ttu-id="1b08b-114">Si el archivo dll o el archivo DLL al que se hace referencia no se encuentra en un directorio especificado por la ruta de acceso, mueva el archivo DLL a un directorio al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="1b08b-114">If the DLL or referenced DLL is not in a directory specified by the path, move the DLL to a referenced directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b08b-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="1b08b-115">See also</span></span>

- [<span data-ttu-id="1b08b-116">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="1b08b-116">Declare Statement</span></span>](../statements/declare-statement.md)
