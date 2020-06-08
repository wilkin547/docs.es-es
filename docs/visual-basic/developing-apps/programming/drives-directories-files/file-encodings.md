---
title: Codificaciones de archivos
ms.date: 07/20/2015
helpviewer_keywords:
- character encodings
- files [Visual Basic], encoding
- Unicode, file encoding
- file encoding
ms.assetid: ea2c5f5f-bbb1-4150-9928-b9951fa6bc57
ms.openlocfilehash: f906b2f2d747a7950c70a24549bbf5423e5b87b4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401750"
---
# <a name="file-encodings-visual-basic"></a><span data-ttu-id="ebf7f-102">Codificación de archivos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ebf7f-102">File Encodings (Visual Basic)</span></span>

<span data-ttu-id="ebf7f-103">Las codificaciones de archivos, también denominadas codificaciones de caracteres, especifican cómo se representan los caracteres durante el procesamiento de texto.</span><span class="sxs-lookup"><span data-stu-id="ebf7f-103">File encodings, also known as character encodings, specify how to represent characters when text processing.</span></span> <span data-ttu-id="ebf7f-104">Una codificación puede ser preferible sobre otra por lo que se refiere a los caracteres del lenguaje que puede o no controlar, aunque normalmente se prefiere Unicode.</span><span class="sxs-lookup"><span data-stu-id="ebf7f-104">One encoding may be preferable over another in terms of which language characters it can or cannot handle, although Unicode is usually preferred.</span></span>

<span data-ttu-id="ebf7f-105">Cuando se leen o escriben archivos, la correspondencia incorrecta de las codificaciones de archivo puede producir excepciones o resultados incorrectos.</span><span class="sxs-lookup"><span data-stu-id="ebf7f-105">When reading from or writing to files, improperly matching file encodings may result in exceptions or incorrect results.</span></span>

## <a name="types-of-encodings"></a><span data-ttu-id="ebf7f-106">Tipos de codificaciones</span><span class="sxs-lookup"><span data-stu-id="ebf7f-106">Types of Encodings</span></span>

<span data-ttu-id="ebf7f-107">Unicode es la codificación preferida al trabajar con archivos.</span><span class="sxs-lookup"><span data-stu-id="ebf7f-107">Unicode is the preferred encoding when working with files.</span></span> <span data-ttu-id="ebf7f-108">Unicode es un estándar mundial de codificación de caracteres que usa valores de código de 16 bits para representar todos los caracteres que se usan en la informática moderna, e incluye símbolos técnicos y caracteres especiales que se usan en publicaciones.</span><span class="sxs-lookup"><span data-stu-id="ebf7f-108">Unicode is a worldwide character-encoding standard that uses 16-bit code values to represent all the characters used in modern computing, including technical symbols and special characters used in publishing.</span></span>

<span data-ttu-id="ebf7f-109">Los estándares de codificación de caracteres anteriores constaban de juegos de caracteres tradicionales, como el juego de caracteres ANSI de Windows que usa valores de código de 8 bits, o combinaciones de valores de 8 bits, para representar los caracteres que se usan en un idioma o región geográfica específicos.</span><span class="sxs-lookup"><span data-stu-id="ebf7f-109">Previous character-encoding standards consisted of traditional character sets, such as the Windows ANSI character set that uses 8-bit code values, or combinations of 8-bit values, to represent the characters used in a specific language or geographical region.</span></span>

## <a name="encoding-class"></a><span data-ttu-id="ebf7f-110">Clase Encoding</span><span class="sxs-lookup"><span data-stu-id="ebf7f-110">Encoding Class</span></span>

<span data-ttu-id="ebf7f-111">La clase <xref:System.Text.Encoding> representa una codificación de caracteres.</span><span class="sxs-lookup"><span data-stu-id="ebf7f-111">The <xref:System.Text.Encoding> class represents a character encoding.</span></span> <span data-ttu-id="ebf7f-112">En esta tabla se muestra el tipo de codificaciones disponibles y se describe cada uno.</span><span class="sxs-lookup"><span data-stu-id="ebf7f-112">This table lists the type of encodings available and describes each.</span></span>

|<span data-ttu-id="ebf7f-113">Name</span><span class="sxs-lookup"><span data-stu-id="ebf7f-113">Name</span></span>|<span data-ttu-id="ebf7f-114">Description</span><span class="sxs-lookup"><span data-stu-id="ebf7f-114">Description</span></span>|
|---|---|
|<xref:System.Text.ASCIIEncoding>|<span data-ttu-id="ebf7f-115">Representa una codificación de caracteres ASCII de caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="ebf7f-115">Represents an ASCII character encoding of Unicode characters.</span></span>|
|<xref:System.Text.UnicodeEncoding>|<span data-ttu-id="ebf7f-116">Representa una codificación UTF-16 de caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="ebf7f-116">Represents a UTF-16 encoding of Unicode characters.</span></span>|
|<xref:System.Text.UTF32Encoding>|<span data-ttu-id="ebf7f-117">Representa una codificación UTF-32 de caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="ebf7f-117">Represents a UTF-32 encoding of Unicode characters.</span></span>|
|<xref:System.Text.UTF7Encoding>|<span data-ttu-id="ebf7f-118">Representa una codificación UTF-7 de caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="ebf7f-118">Represents a UTF-7 encoding of Unicode characters.</span></span>|
|<xref:System.Text.UTF8Encoding>|<span data-ttu-id="ebf7f-119">Representa una codificación UTF-8 de caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="ebf7f-119">Represents a UTF-8 encoding of Unicode characters.</span></span>|

## <a name="see-also"></a><span data-ttu-id="ebf7f-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="ebf7f-120">See also</span></span>

- [<span data-ttu-id="ebf7f-121">Leer archivos</span><span class="sxs-lookup"><span data-stu-id="ebf7f-121">Reading from Files</span></span>](reading-from-files.md)
- [<span data-ttu-id="ebf7f-122">Escritura en archivos</span><span class="sxs-lookup"><span data-stu-id="ebf7f-122">Writing to Files</span></span>](writing-to-files.md)
