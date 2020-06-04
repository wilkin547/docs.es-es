---
title: <membername> no compatible con CLS no se permite en una interfaz compatible con CLS
ms.date: 07/20/2015
f1_keywords:
- bc40033
- vbc40033
helpviewer_keywords:
- BC40033
ms.assetid: 060c4b08-798e-40f1-94cf-c05c524f1b8a
ms.openlocfilehash: e572189b958612bf9527c82ce702df3ab929a23f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409405"
---
# <a name="non-cls-compliant-membername-is-not-allowed-in-a-cls-compliant-interface"></a>\<membername> no compatible con CLS no se permite en una interfaz compatible con CLS
Una propiedad, un procedimiento o un evento de una interfaz se marca como `<CLSCompliant(True)>` cuando la propia interfaz está marcada como `<CLSCompliant(False)>` o no está marcada.  
  
 Para que una interfaz sea compatible con la [independencia del lenguaje y componentes independientes del lenguaje](../../../standard/language-independence-and-language-independent-components.md) (CLS), todos sus miembros deben ser conformes.  
  
 Al aplicar <xref:System.CLSCompliantAttribute> a un elemento de programación, establezca el parámetro `isCompliant` del atributo en `True` o `False` para indicar conformidad o disconformidad. No hay ningún valor predeterminado para este parámetro, por lo que debe proporcionar uno.  
  
 Si no se aplica <xref:System.CLSCompliantAttribute> a un elemento, se considera que no es conforme.  
  
 De forma predeterminada, este mensaje es una advertencia. Para obtener información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Identificador de error:** BC40033  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Si requiere la conformidad con CLS y tiene control sobre el código fuente de la interfaz, marque la interfaz como `<CLSCompliant(True)>` si todos sus miembros son conformes.  
  
- Si requiere conformidad con CLS y no tiene control sobre el código fuente de la interfaz, o si no cumple los requisitos, defina este miembro dentro de una interfaz diferente.  
  
- Si requiere que este miembro permanezca dentro de su interfaz actual, quite el <xref:System.CLSCompliantAttribute> de su definición o márquelo como `<CLSCompliant(False)>` .  
  
## <a name="see-also"></a>Consulte también

- [Instrucción Interface](../statements/interface-statement.md)
