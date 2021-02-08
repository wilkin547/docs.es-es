---
description: 'Más información acerca de: literales (Entity SQL)'
title: Literales (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 092ef693-6e5f-41b4-b868-5b9e82928abf
ms.openlocfilehash: cae2ec7ab8cf19166dc3100a85473fca2ed0a7be
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791886"
---
# <a name="literals-entity-sql"></a>Literales (Entity SQL)

En este tema se describe la compatibilidad con los literales en [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
## <a name="null"></a>Null  

 El literal null se utiliza para representar valores null de cualquier tipo. Un literal null es compatible con todos los tipos.  
  
 Los valores null con tipo se pueden crear realizando una conversión de un literal null. Para obtener más información, vea [Cast](cast-entity-sql.md).  
  
 Para las reglas sobre dónde se pueden usar los literales null flotantes, vea [literales null e inferencia de tipos](null-literals-and-type-inference-entity-sql.md).  
  
## <a name="boolean"></a>Boolean  

 Los literales booleanos se representan mediante las palabras clave `true` y `false`.  
  
## <a name="integer"></a>Entero  

 Los literales enteros pueden ser de tipo <xref:System.Int32> o <xref:System.Int64>. Un literal <xref:System.Int32> es una serie de caracteres numéricos. Un literal <xref:System.Int64> es una serie de caracteres numéricos seguidos de una letra L en mayúsculas.  
  
## <a name="decimal"></a>Decimal  

 Un número de punto fijo (decimal) es una serie de caracteres numéricos, un punto (.) y otra serie de caracteres numéricos seguidos de una letra "M" en mayúsculas.  
  
## <a name="float-double"></a>Flotante y doble  

 Un número de punto flotante de doble precisión es una serie de caracteres numéricos, un punto (.) y otra serie de caracteres numéricos seguidos, posiblemente, de un exponente. Un número de punto flotante de precisión sencilla (o float) es un número de punto flotante de precisión doble seguido de la letra f en minúsculas.  
  
## <a name="string"></a>String  

 Una cadena es una serie de caracteres incluidos entre comillas. Las comillas pueden ser simples (`'`) o dobles ("). Los literales de cadenas de caracteres pueden ser Unicode o no Unicode. Para declarar un literal de cadena de caracteres como Unicode, anteponga al literal la letra "N" mayúscula. De forma predeterminada, son literales de cadena de caracteres no Unicode. No puede haber espacios entre la N y la carga del literal de cadena, y la N debe estar en mayúsculas.  
  
```sql  
'hello' -- non-Unicode character string literal  
N'hello' -- Unicode character string literal  
"x"  
N"This is a string!"  
'so is THIS'  
```  
  
## <a name="datetime"></a>DateTime  

 Un literal datetime es independiente de la configuración regional y está compuesto de una fecha y una hora. Tanto la fecha como la hora deben aparecer y no hay valores predeterminados.  
  
 La parte de la fecha debe tener el formato: `YYYY` - `MM` - `DD` , donde `YYYY` es un valor de año de cuatro dígitos entre 0001 y 9999, `MM` es el mes comprendido entre 1 y 12 y `DD` es el valor de día válido para el mes determinado `MM` .  
  
 La hora debe tener el formato: `HH`:`MM`[:`SS`[.fffffff]], donde `HH` es el valor correspondiente a la hora comprendido entre 0 y 23, `MM` es el valor correspondiente a los minutos comprendido entre 0 y 59, `SS` es el valor correspondiente a los segundos comprendido entre 0 y 59, y fffffff es el valor correspondiente a la fracción de segundo comprendido entre 0 y 9999999. Todos los intervalos de valores incluyen los valores extremos. Las fracciones de segundo son opcionales. Los segundos son opcionales a menos que se especifiquen fracciones de segundo; en este caso, los segundos son necesarios. Cuando no se especifican segundos o fracciones de segundo, se usa el valor cero predeterminado.  
  
 Puede haber cualquier número de espacios entre el símbolo DATETIME y la carga del literal, pero no puede haber líneas nuevas.  
  
```sql  
DATETIME'2006-10-1 23:11'  
DATETIME'2006-12-25 01:01:00.0000000' -- same as DATETIME'2006-12-25 01:01'  
```  
  
## <a name="time"></a>Hora  

 Un literal time es independiente de la configuración regional y está compuesto de una hora exclusivamente. La hora debe aparecer y no hay ningún valor predeterminado. Debe tener el formato HH:MM[:SS[.fffffff]], donde HH es el valor correspondiente a la hora comprendido entre 0 y 23, MM es el valor correspondiente a los minutos comprendido entre 0 y 59, SS es el valor correspondiente a los segundos comprendido entre 0 y 59, y fffffff es el valor correspondiente a la fracción de segundo comprendido entre 0 y 9999999. Todos los intervalos de valores incluyen los valores extremos. Las fracciones de segundo son opcionales. Los segundos son opcionales a menos que se especifiquen fracciones de segundo; en este caso, los segundos son necesarios. Cuando no se especifican segundos o fracciones de segundo, se usa el valor cero predeterminado.  
  
 Puede haber cualquier número de espacios entre el símbolo TIME y la carga del literal, pero no puede haber líneas nuevas.  
  
```sql  
TIME‘23:11’  
TIME‘01:01:00.1234567’  
```  
  
## <a name="datetimeoffset"></a>DateTimeOffset  

 Un literal datetimeoffset es independiente de la configuración regional y está compuesto de una fecha, una hora y un desplazamiento. La fecha, la hora y el desplazamiento deben aparecer y no hay valores predeterminados. La fecha debe tener el formato YYYY-MM-DD, donde YYYY es un valor de cuatro dígitos correspondiente al año comprendido entre 0001 y 9999, MM es el valor correspondiente al mes comprendido entre 1 y 12, y DD es el valor correspondiente al día, que tiene que ser válido para el mes especificado. La hora debe tener el formato HH:MM[:SS[.fffffff]], donde HH es el valor correspondiente a la hora comprendido entre 0 y 23, MM es el valor correspondiente a los minutos comprendido entre 0 y 59, SS es el valor correspondiente a los segundos comprendido entre 0 y 59, y fffffff es el valor correspondiente a la fracción de segundo comprendido entre 0 y 9999999. Todos los intervalos de valores incluyen los valores extremos. Las fracciones de segundo son opcionales. Los segundos son opcionales a menos que se especifiquen fracciones de segundo; en este caso, los segundos son necesarios. Cuando no se especifican segundos o fracciones de segundo, se usa el valor cero predeterminado. La parte de desplazamiento debe tener el formato {+&#124;-} HH: MM, donde HH y MM tienen el mismo significado que en la parte de hora. Sin embargo, el desplazamiento debe estar comprendido entre -14:00 y + 14:00.  
  
 Puede haber cualquier número de espacios entre el símbolo DATETIMEOFFSET y la carga del literal, pero no puede haber líneas nuevas.  
  
```sql  
DATETIMEOFFSET‘2006-10-1 23:11 +02:00’  
DATETIMEOFFSET‘2006-12-25 01:01:00.0000000 -08:30’  
```  
  
> [!NOTE]
> Un valor literal de Entity SQL válido puede quedar fuera de los intervalos admitidos para CLR o el origen de datos. Esto puede dar lugar a una excepción.  
  
## <a name="binary"></a>Binary  

 Un literal de cadena binario (binary) es una secuencia de dígitos hexadecimales delimitados por comillas simples que sigue a la palabra clave binary, al símbolo de método abreviado `X` o `x`. El símbolo de método abreviado `X` no distingue entre mayúsculas y minúsculas. Se permite que haya espacios entre la palabra clave `binary` y el valor de la cadena binaria.  
  
 Los caracteres hexadecimales tampoco distinguen mayúsculas de minúsculas. Si el literal está compuesto de un número impar de dígitos hexadecimales, el literal se alineará con el siguiente dígito hexadecimal par anteponiéndole un dígito cero hexadecimal. No hay ningún límite formal para el tamaño de la cadena binaria.  
  
```sql  
Binary'00ffaabb'  
X'ABCabc'  
BINARY    '0f0f0f0F0F0F0F0F0F0F'  
X'' –- empty binary string  
```  
  
## <a name="guid"></a>Guid  

 Un literal `GUID` representa un identificador único global. Es una secuencia formada por la palabra clave `GUID` seguida de dígitos hexadecimales en el formato denominado *registro* : 8-4-4-4-12 entre comillas simples. Los dígitos hexadecimales no distinguen mayúsculas de minúsculas.  
  
 Puede haber cualquier número de espacios entre el símbolo GUID y la carga del literal, pero no puede haber líneas nuevas.  
  
```sql  
Guid'1afc7f5c-ffa0-4741-81cf-f12eAAb822bf'  
GUID  '1AFC7F5C-FFA0-4741-81CF-F12EAAB822BF'  
```  
  
## <a name="see-also"></a>Vea también

- [Información general sobre Entity SQL](entity-sql-overview.md)
