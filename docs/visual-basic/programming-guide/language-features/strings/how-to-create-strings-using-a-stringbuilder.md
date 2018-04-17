---
title: 'Cómo: Crear cadenas mediante un objeto StringBuilder en Visual Basic'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c0e15c7df07822ee104a88525c209768c05470e3
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a>Cómo: Crear cadenas mediante un objeto StringBuilder en Visual Basic
Este ejemplo crea una cadena larga de muchas cadenas más pequeñas mediante la <xref:System.Text.StringBuilder> clase. El <xref:System.Text.StringBuilder> clase es más eficaz que la `&=` operador para concatenar muchas cadenas.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea una instancia de la <xref:System.Text.StringBuilder> (clase), anexan 1.000 cadenas a esa instancia y, a continuación, devuelve la representación de cadena.  
  
 [!code-vb[VbVbalrStrings#70](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-create-strings-using-a-stringbuilder_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Utilizar la clase StringBuilder](../../../../standard/base-types/stringbuilder.md)  
 [Operador &=](../../../../visual-basic/language-reference/operators/and-assignment-operator.md)  
 [Cadenas](../../../../visual-basic/programming-guide/language-features/strings/index.md)  
 [Creación de cadenas nuevas](../../../../standard/base-types/creating-new.md)  
 [Manipular cadenas](../../../../standard/base-types/manipulating-strings.md)  
 [Ejemplo de cadenas](https://msdn.microsoft.com/library/be9e82a3-dc95-4aaa-9396-61b66e467e02(v=vs.100))
