---
title: "&lt;proceduresignature1&gt; no es conforme a CLS porque sobrecarga &lt;proceduresignature2&gt; que difiere de él en la matriz de tipos de parámetro de matriz o el rango de los tipos de parámetro de matriz"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40035
- bc40035
helpviewer_keywords:
- BC40035
ms.assetid: 50a66dbe-2c1e-41bf-96bc-369301c891ac
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d361759471a8edfa97437bd2503cfaa661fb9678
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/21/2017
---
# <a name="ltproceduresignature1gt-is-not-cls-compliant-because-it-overloads-ltproceduresignature2gt-which-differs-from-it-only-by-array-of-array-parameter-types-or-by-the-rank-of-the-array-parameter-types"></a>&lt;proceduresignature1&gt; no es conforme a CLS porque sobrecarga &lt;proceduresignature2&gt; que difiere de él en la matriz de tipos de parámetro de matriz o el rango de los tipos de parámetro de matriz
Un procedimiento o propiedad está marcada como `<CLSCompliant(True)>` cuando reemplaza otro procedimiento o propiedad y la única diferencia entre sus listas de parámetros es el nivel de anidamiento de una matriz escalonada o el rango de una matriz.  
  
 En las declaraciones siguientes, la segunda y tercera declaraciones generan este error.  
  
 `Overloads Sub processArray(ByVal arrayParam() As Integer)`  
  
 `Overloads Sub processArray(ByVal arrayParam()() As Integer)`  
  
 `Overloads Sub processArray(ByVal arrayParam(,) As Integer)`  
  
 La segunda declaración cambia el parámetro unidimensional original `arrayParam` a una matriz de matrices. Los cambios en la terceros declaración `arrayParam` a una matriz bidimensional (rango 2). Aunque Visual Basic permite sobrecargas para solamente se distinguen por uno de estos cambios, la sobrecarga de este tipo no es compatible con la [independencia del lenguaje y componentes independientes del lenguaje](../../../standard/language-independence-and-language-independent-components.md) (CLS).  
  
 Al aplicar <xref:System.CLSCompliantAttribute> a un elemento de programación, establezca el parámetro `isCompliant` del atributo en `True` o `False` para indicar conformidad o disconformidad. No hay ningún valor predeterminado para este parámetro y debe proporcionar un valor.  
  
 Si no se aplica <xref:System.CLSCompliantAttribute> a un elemento, se considera que no es conforme.  
  
 De forma predeterminada, este mensaje es una advertencia. Para obtener información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Id. de error:** BC40035  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Si necesita conformidad con CLS, defina sus sobrecargas para que coincidan entre sí de más formas que solo los cambios mencionados en esta página de ayuda.  
  
-   Si necesita que las sobrecargas difieren solo por los cambios mencionados en esta ayuda página, quite el <xref:System.CLSCompliantAttribute> de sus definiciones o se marcan como `<CLSCompliant(False)>`.  
  
## <a name="see-also"></a>Vea también  
   
 [Sobrecarga de procedimientos](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)  
 [Sobrecargas](../../../visual-basic/language-reference/modifiers/overloads.md)
