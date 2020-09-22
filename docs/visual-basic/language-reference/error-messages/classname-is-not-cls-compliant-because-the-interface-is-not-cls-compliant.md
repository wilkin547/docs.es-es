---
title: La clase '<classname>' no es compatible con CLS porque la interfaz '<interfacename>' que implementa tampoco lo es
ms.date: 07/20/2015
f1_keywords:
- bc40029
- vbc40029
helpviewer_keywords:
- BC40029
ms.assetid: 178452f3-5575-4da0-9d6c-53bcddb6a338
ms.openlocfilehash: a482d14094a3fa86b56ca84af46c45e6093416c5
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874632"
---
# <a name="classname-is-not-cls-compliant-because-the-interface-interfacename-it-implements-is-not-cls-compliant"></a>La clase '\<classname>' no es compatible con CLS porque la interfaz '\<interfacename>' que implementa tampoco lo es

Una clase o interfaz se marca como `<CLSCompliant(True)>` cuando se deriva (o lo implementa) de un tipo marcado como `<CLSCompliant(False)>` o que no está marcado.  
  
 Para que una clase o interfaz sea compatible con la [independencia del lenguaje y componentes independientes del lenguaje](../../../standard/language-independence-and-language-independent-components.md) (CLS), toda su jerarquía de herencia debe ser compatible. Esto significa que cada tipo del que hereda, directa o indirectamente, debe ser compatible. De forma similar, si una clase implementa una o varias interfaces, todas deben conformes a lo largo de su jerarquía de herencia.  
  
 Al aplicar <xref:System.CLSCompliantAttribute> a un elemento de programación, establezca el parámetro `isCompliant` del atributo en `True` o `False` para indicar conformidad o disconformidad. No hay ningún valor predeterminado para este parámetro, por lo que debe proporcionar uno.  
  
 Si no se aplica <xref:System.CLSCompliantAttribute> a un elemento, se considera que no es conforme.  
  
 De forma predeterminada, este mensaje es una advertencia. Para obtener información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Identificador de error:** BC40029  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Si necesita compatibilidad con CLS, defina este tipo dentro de una jerarquía de herencia diferente para el esquema de implementación.  
  
- Si requiere que este tipo permanezca dentro de su esquema de implementación o de la jerarquía de herencia actuales, quite el <xref:System.CLSCompliantAttribute> de su definición o márquelo como `<CLSCompliant(False)>`.  
