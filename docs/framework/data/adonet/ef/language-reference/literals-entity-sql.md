---
title: Literales (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 092ef693-6e5f-41b4-b868-5b9e82928abf
ms.openlocfilehash: 4402f4c6ee38432a0f606e39dd4a18639076ce04
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91161781"
---
# <a name="literals-entity-sql"></a><span data-ttu-id="93b22-102">Literales (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="93b22-102">Literals (Entity SQL)</span></span>

<span data-ttu-id="93b22-103">En este tema se describe la compatibilidad con los literales en [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="93b22-103">This topic describes [!INCLUDE[esql](../../../../../../includes/esql-md.md)] support for literals.</span></span>  
  
## <a name="null"></a><span data-ttu-id="93b22-104">Null</span><span class="sxs-lookup"><span data-stu-id="93b22-104">Null</span></span>  

 <span data-ttu-id="93b22-105">El literal null se utiliza para representar valores null de cualquier tipo.</span><span class="sxs-lookup"><span data-stu-id="93b22-105">The null literal is used to represent the value null for any type.</span></span> <span data-ttu-id="93b22-106">Un literal null es compatible con todos los tipos.</span><span class="sxs-lookup"><span data-stu-id="93b22-106">A null literal is compatible with any type.</span></span>  
  
 <span data-ttu-id="93b22-107">Los valores null con tipo se pueden crear realizando una conversión de un literal null.</span><span class="sxs-lookup"><span data-stu-id="93b22-107">Typed nulls can be created by a cast over a null literal.</span></span> <span data-ttu-id="93b22-108">Para obtener más información, vea [Cast](cast-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="93b22-108">For more information, see [CAST](cast-entity-sql.md).</span></span>  
  
 <span data-ttu-id="93b22-109">Para las reglas sobre dónde se pueden usar los literales null flotantes, vea [literales null e inferencia de tipos](null-literals-and-type-inference-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="93b22-109">For rules about where free floating null literals can be used, see [Null Literals and Type Inference](null-literals-and-type-inference-entity-sql.md).</span></span>  
  
## <a name="boolean"></a><span data-ttu-id="93b22-110">Boolean</span><span class="sxs-lookup"><span data-stu-id="93b22-110">Boolean</span></span>  

 <span data-ttu-id="93b22-111">Los literales booleanos se representan mediante las palabras clave `true` y `false`.</span><span class="sxs-lookup"><span data-stu-id="93b22-111">Boolean literals are represented by the keywords `true` and `false`.</span></span>  
  
## <a name="integer"></a><span data-ttu-id="93b22-112">Entero</span><span class="sxs-lookup"><span data-stu-id="93b22-112">Integer</span></span>  

 <span data-ttu-id="93b22-113">Los literales enteros pueden ser de tipo <xref:System.Int32> o <xref:System.Int64>.</span><span class="sxs-lookup"><span data-stu-id="93b22-113">Integer literals can be of type <xref:System.Int32> or <xref:System.Int64>.</span></span> <span data-ttu-id="93b22-114">Un literal <xref:System.Int32> es una serie de caracteres numéricos.</span><span class="sxs-lookup"><span data-stu-id="93b22-114">An <xref:System.Int32> literal is a series of numeric characters.</span></span> <span data-ttu-id="93b22-115">Un literal <xref:System.Int64> es una serie de caracteres numéricos seguidos de una letra L en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="93b22-115">An <xref:System.Int64> literal is series of numeric characters followed by an uppercase L.</span></span>  
  
## <a name="decimal"></a><span data-ttu-id="93b22-116">Decimal</span><span class="sxs-lookup"><span data-stu-id="93b22-116">Decimal</span></span>  

 <span data-ttu-id="93b22-117">Un número de punto fijo (decimal) es una serie de caracteres numéricos, un punto (.) y otra serie de caracteres numéricos seguidos de una letra "M" en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="93b22-117">A fixed-point number (decimal) is a series of numeric characters, a dot (.) and another series of numeric characters followed by an uppercase "M".</span></span>  
  
## <a name="float-double"></a><span data-ttu-id="93b22-118">Flotante y doble</span><span class="sxs-lookup"><span data-stu-id="93b22-118">Float, Double</span></span>  

 <span data-ttu-id="93b22-119">Un número de punto flotante de doble precisión es una serie de caracteres numéricos, un punto (.) y otra serie de caracteres numéricos seguidos, posiblemente, de un exponente.</span><span class="sxs-lookup"><span data-stu-id="93b22-119">A double-precision floating point number is a series of numeric characters, a dot (.) and another series of numeric characters possibly followed by an exponent.</span></span> <span data-ttu-id="93b22-120">Un número de punto flotante de precisión sencilla (o float) es un número de punto flotante de precisión doble seguido de la letra f en minúsculas.</span><span class="sxs-lookup"><span data-stu-id="93b22-120">A single-precisions floating point number (or float) is a double-precision floating point number syntax followed by the lowercase f.</span></span>  
  
## <a name="string"></a><span data-ttu-id="93b22-121">String</span><span class="sxs-lookup"><span data-stu-id="93b22-121">String</span></span>  

 <span data-ttu-id="93b22-122">Una cadena es una serie de caracteres incluidos entre comillas.</span><span class="sxs-lookup"><span data-stu-id="93b22-122">A string is a series of characters enclosed in quote marks.</span></span> <span data-ttu-id="93b22-123">Las comillas pueden ser simples (`'`) o dobles (").</span><span class="sxs-lookup"><span data-stu-id="93b22-123">Quotes can be either both single-quotes (`'`) or both double-quotes (").</span></span> <span data-ttu-id="93b22-124">Los literales de cadenas de caracteres pueden ser Unicode o no Unicode.</span><span class="sxs-lookup"><span data-stu-id="93b22-124">Character string literals can be either Unicode or non-Unicode.</span></span> <span data-ttu-id="93b22-125">Para declarar un literal de cadena de caracteres como Unicode, anteponga al literal la letra "N" mayúscula.</span><span class="sxs-lookup"><span data-stu-id="93b22-125">To declare a character string literal as Unicode, prefix the literal with an uppercase "N".</span></span> <span data-ttu-id="93b22-126">De forma predeterminada, son literales de cadena de caracteres no Unicode.</span><span class="sxs-lookup"><span data-stu-id="93b22-126">The default is non-Unicode character string literals.</span></span> <span data-ttu-id="93b22-127">No puede haber espacios entre la N y la carga del literal de cadena, y la N debe estar en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="93b22-127">There can be no spaces between the N and the string literal payload, and the N must be uppercase.</span></span>  
  
```sql  
'hello' -- non-Unicode character string literal  
N'hello' -- Unicode character string literal  
"x"  
N"This is a string!"  
'so is THIS'  
```  
  
## <a name="datetime"></a><span data-ttu-id="93b22-128">DateTime</span><span class="sxs-lookup"><span data-stu-id="93b22-128">DateTime</span></span>  

 <span data-ttu-id="93b22-129">Un literal datetime es independiente de la configuración regional y está compuesto de una fecha y una hora.</span><span class="sxs-lookup"><span data-stu-id="93b22-129">A datetime literal is independent of locale and is composed of a date part and a time part.</span></span> <span data-ttu-id="93b22-130">Tanto la fecha como la hora deben aparecer y no hay valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="93b22-130">Both date and time parts are mandatory and there are no default values.</span></span>  
  
 <span data-ttu-id="93b22-131">La parte de la fecha debe tener el formato: `YYYY` - `MM` - `DD` , donde `YYYY` es un valor de año de cuatro dígitos entre 0001 y 9999, `MM` es el mes comprendido entre 1 y 12 y `DD` es el valor de día válido para el mes determinado `MM` .</span><span class="sxs-lookup"><span data-stu-id="93b22-131">The date part must have the format: `YYYY`-`MM`-`DD`, where `YYYY` is a four digit year value between 0001 and 9999, `MM` is the month between 1 and 12 and `DD` is the day value that is valid for the given month `MM`.</span></span>  
  
 <span data-ttu-id="93b22-132">La hora debe tener el formato: `HH`:`MM`[:`SS`[.fffffff]], donde `HH` es el valor correspondiente a la hora comprendido entre 0 y 23, `MM` es el valor correspondiente a los minutos comprendido entre 0 y 59, `SS` es el valor correspondiente a los segundos comprendido entre 0 y 59, y fffffff es el valor correspondiente a la fracción de segundo comprendido entre 0 y 9999999.</span><span class="sxs-lookup"><span data-stu-id="93b22-132">The time part must have the format: `HH`:`MM`[:`SS`[.fffffff]], where `HH` is the hour value between 0 and 23, `MM` is the minute value between 0 and 59, `SS` is the second value between 0 and 59 and fffffff is the fractional second value between 0 and 9999999.</span></span> <span data-ttu-id="93b22-133">Todos los intervalos de valores incluyen los valores extremos.</span><span class="sxs-lookup"><span data-stu-id="93b22-133">All value ranges are inclusive.</span></span> <span data-ttu-id="93b22-134">Las fracciones de segundo son opcionales.</span><span class="sxs-lookup"><span data-stu-id="93b22-134">Fractional seconds are optional.</span></span> <span data-ttu-id="93b22-135">Los segundos son opcionales a menos que se especifiquen fracciones de segundo; en este caso, los segundos son necesarios.</span><span class="sxs-lookup"><span data-stu-id="93b22-135">Seconds are optional unless fractional seconds are specified; in this case, seconds are required.</span></span> <span data-ttu-id="93b22-136">Cuando no se especifican segundos o fracciones de segundo, se usa el valor cero predeterminado.</span><span class="sxs-lookup"><span data-stu-id="93b22-136">When seconds or fractional seconds are not specified, the default value of zero will be used instead.</span></span>  
  
 <span data-ttu-id="93b22-137">Puede haber cualquier número de espacios entre el símbolo DATETIME y la carga del literal, pero no puede haber líneas nuevas.</span><span class="sxs-lookup"><span data-stu-id="93b22-137">There can be any number of spaces between the DATETIME symbol and the literal payload, but no new lines.</span></span>  
  
```sql  
DATETIME'2006-10-1 23:11'  
DATETIME'2006-12-25 01:01:00.0000000' -- same as DATETIME'2006-12-25 01:01'  
```  
  
## <a name="time"></a><span data-ttu-id="93b22-138">Time</span><span class="sxs-lookup"><span data-stu-id="93b22-138">Time</span></span>  

 <span data-ttu-id="93b22-139">Un literal time es independiente de la configuración regional y está compuesto de una hora exclusivamente.</span><span class="sxs-lookup"><span data-stu-id="93b22-139">A time literal is independent of locale and composed of a time part only.</span></span> <span data-ttu-id="93b22-140">La hora debe aparecer y no hay ningún valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="93b22-140">The time part is mandatory and there is no default value.</span></span> <span data-ttu-id="93b22-141">Debe tener el formato HH:MM[:SS[.fffffff]], donde HH es el valor correspondiente a la hora comprendido entre 0 y 23, MM es el valor correspondiente a los minutos comprendido entre 0 y 59, SS es el valor correspondiente a los segundos comprendido entre 0 y 59, y fffffff es el valor correspondiente a la fracción de segundo comprendido entre 0 y 9999999.</span><span class="sxs-lookup"><span data-stu-id="93b22-141">It must have the format HH:MM[:SS[.fffffff]], where HH is the hour value between 0 and 23, MM is the minute value between 0 and 59, SS is the second value between 0 and 59, and fffffff is the second fraction value between 0 and 9999999.</span></span> <span data-ttu-id="93b22-142">Todos los intervalos de valores incluyen los valores extremos.</span><span class="sxs-lookup"><span data-stu-id="93b22-142">All value ranges are inclusive.</span></span> <span data-ttu-id="93b22-143">Las fracciones de segundo son opcionales.</span><span class="sxs-lookup"><span data-stu-id="93b22-143">Fractional seconds are optional.</span></span> <span data-ttu-id="93b22-144">Los segundos son opcionales a menos que se especifiquen fracciones de segundo; en este caso, los segundos son necesarios.</span><span class="sxs-lookup"><span data-stu-id="93b22-144">Seconds are optional unless fractional seconds are specified; in this case, seconds are required.</span></span> <span data-ttu-id="93b22-145">Cuando no se especifican segundos o fracciones de segundo, se usa el valor cero predeterminado.</span><span class="sxs-lookup"><span data-stu-id="93b22-145">When seconds or fractions are not specified, the default value of zero will be used instead.</span></span>  
  
 <span data-ttu-id="93b22-146">Puede haber cualquier número de espacios entre el símbolo TIME y la carga del literal, pero no puede haber líneas nuevas.</span><span class="sxs-lookup"><span data-stu-id="93b22-146">There can be any number of spaces between the TIME symbol and the literal payload, but no new lines.</span></span>  
  
```sql  
TIME‘23:11’  
TIME‘01:01:00.1234567’  
```  
  
## <a name="datetimeoffset"></a><span data-ttu-id="93b22-147">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="93b22-147">DateTimeOffset</span></span>  

 <span data-ttu-id="93b22-148">Un literal datetimeoffset es independiente de la configuración regional y está compuesto de una fecha, una hora y un desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="93b22-148">A datetimeoffset literal is independent of locale and composed of a date part, a time part, and an offset part.</span></span> <span data-ttu-id="93b22-149">La fecha, la hora y el desplazamiento deben aparecer y no hay valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="93b22-149">All date, time, and offset parts are mandatory and there are no default values.</span></span> <span data-ttu-id="93b22-150">La fecha debe tener el formato YYYY-MM-DD, donde YYYY es un valor de cuatro dígitos correspondiente al año comprendido entre 0001 y 9999, MM es el valor correspondiente al mes comprendido entre 1 y 12, y DD es el valor correspondiente al día, que tiene que ser válido para el mes especificado.</span><span class="sxs-lookup"><span data-stu-id="93b22-150">The date part must have the format YYYY-MM-DD, where YYYY is a four digit year value between 0001 and 9999, MM is the month between 1 and 12, and DD is the day value that is valid for the given month.</span></span> <span data-ttu-id="93b22-151">La hora debe tener el formato HH:MM[:SS[.fffffff]], donde HH es el valor correspondiente a la hora comprendido entre 0 y 23, MM es el valor correspondiente a los minutos comprendido entre 0 y 59, SS es el valor correspondiente a los segundos comprendido entre 0 y 59, y fffffff es el valor correspondiente a la fracción de segundo comprendido entre 0 y 9999999.</span><span class="sxs-lookup"><span data-stu-id="93b22-151">The time part must have the format HH:MM[:SS[.fffffff]], where HH is the hour value between 0 and 23, MM is the minute value between 0 and 59, SS is the second value between 0 and 59, and fffffff is the fractional second value between 0 and 9999999.</span></span> <span data-ttu-id="93b22-152">Todos los intervalos de valores incluyen los valores extremos.</span><span class="sxs-lookup"><span data-stu-id="93b22-152">All value ranges are inclusive.</span></span> <span data-ttu-id="93b22-153">Las fracciones de segundo son opcionales.</span><span class="sxs-lookup"><span data-stu-id="93b22-153">Fractional seconds are optional.</span></span> <span data-ttu-id="93b22-154">Los segundos son opcionales a menos que se especifiquen fracciones de segundo; en este caso, los segundos son necesarios.</span><span class="sxs-lookup"><span data-stu-id="93b22-154">Seconds are optional unless fractional seconds are specified; in this case, seconds are required.</span></span> <span data-ttu-id="93b22-155">Cuando no se especifican segundos o fracciones de segundo, se usa el valor cero predeterminado.</span><span class="sxs-lookup"><span data-stu-id="93b22-155">When seconds or fractions are not specified, the default value of zero will be used instead.</span></span> <span data-ttu-id="93b22-156">La parte de desplazamiento debe tener el formato {+&#124;-} HH: MM, donde HH y MM tienen el mismo significado que en la parte de hora.</span><span class="sxs-lookup"><span data-stu-id="93b22-156">The offset part must have the format {+&#124;-}HH:MM, where HH and MM have the same meaning as in the time part.</span></span> <span data-ttu-id="93b22-157">Sin embargo, el desplazamiento debe estar comprendido entre -14:00 y + 14:00.</span><span class="sxs-lookup"><span data-stu-id="93b22-157">The range of the offset, however, must be between -14:00 and + 14:00</span></span>  
  
 <span data-ttu-id="93b22-158">Puede haber cualquier número de espacios entre el símbolo DATETIMEOFFSET y la carga del literal, pero no puede haber líneas nuevas.</span><span class="sxs-lookup"><span data-stu-id="93b22-158">There can be any number of spaces between the DATETIMEOFFSET symbol and the literal payload, but no new lines.</span></span>  
  
```sql  
DATETIMEOFFSET‘2006-10-1 23:11 +02:00’  
DATETIMEOFFSET‘2006-12-25 01:01:00.0000000 -08:30’  
```  
  
> [!NOTE]
> <span data-ttu-id="93b22-159">Un valor literal de Entity SQL válido puede quedar fuera de los intervalos admitidos para CLR o el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="93b22-159">A valid Entity SQL literal value can fall outside the supported ranges for CLR or the data source.</span></span> <span data-ttu-id="93b22-160">Esto puede dar lugar a una excepción.</span><span class="sxs-lookup"><span data-stu-id="93b22-160">This might result in an exception</span></span>  
  
## <a name="binary"></a><span data-ttu-id="93b22-161">Binary</span><span class="sxs-lookup"><span data-stu-id="93b22-161">Binary</span></span>  

 <span data-ttu-id="93b22-162">Un literal de cadena binario (binary) es una secuencia de dígitos hexadecimales delimitados por comillas simples que sigue a la palabra clave binary, al símbolo de método abreviado `X` o `x`.</span><span class="sxs-lookup"><span data-stu-id="93b22-162">A binary string literal is a sequence of hexadecimal digits delimited by single quotes following the keyword binary or the shortcut symbol `X` or `x`.</span></span> <span data-ttu-id="93b22-163">El símbolo de método abreviado `X` no distingue entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="93b22-163">The shortcut symbol `X` is case insensitive.</span></span> <span data-ttu-id="93b22-164">Se permite que haya espacios entre la palabra clave `binary` y el valor de la cadena binaria.</span><span class="sxs-lookup"><span data-stu-id="93b22-164">A zero or more spaces are allowed between the keyword `binary` and the binary string value.</span></span>  
  
 <span data-ttu-id="93b22-165">Los caracteres hexadecimales tampoco distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="93b22-165">Hexadecimal characters are also case insensitive.</span></span> <span data-ttu-id="93b22-166">Si el literal está compuesto de un número impar de dígitos hexadecimales, el literal se alineará con el siguiente dígito hexadecimal par anteponiéndole un dígito cero hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="93b22-166">If the literal is composed of an odd number of hexadecimal digits, the literal will be aligned to the next even hexadecimal digit by prefixing the literal with a hexadecimal zero digit.</span></span> <span data-ttu-id="93b22-167">No hay ningún límite formal para el tamaño de la cadena binaria.</span><span class="sxs-lookup"><span data-stu-id="93b22-167">There is no formal limit on the size of the binary string.</span></span>  
  
```sql  
Binary'00ffaabb'  
X'ABCabc'  
BINARY    '0f0f0f0F0F0F0F0F0F0F'  
X'' –- empty binary string  
```  
  
## <a name="guid"></a><span data-ttu-id="93b22-168">Guid</span><span class="sxs-lookup"><span data-stu-id="93b22-168">Guid</span></span>  

 <span data-ttu-id="93b22-169">Un literal `GUID` representa un identificador único global.</span><span class="sxs-lookup"><span data-stu-id="93b22-169">A `GUID` literal represents a globally unique identifier.</span></span> <span data-ttu-id="93b22-170">Es una secuencia formada por la palabra clave `GUID` seguida de dígitos hexadecimales en el formato denominado *registro* : 8-4-4-4-12 entre comillas simples.</span><span class="sxs-lookup"><span data-stu-id="93b22-170">It is a sequence formed by the keyword `GUID` followed by hexadecimal digits in the form known as *registry* format: 8-4-4-4-12 enclosed in single quotes.</span></span> <span data-ttu-id="93b22-171">Los dígitos hexadecimales no distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="93b22-171">Hexadecimal digits are case insensitive.</span></span>  
  
 <span data-ttu-id="93b22-172">Puede haber cualquier número de espacios entre el símbolo GUID y la carga del literal, pero no puede haber líneas nuevas.</span><span class="sxs-lookup"><span data-stu-id="93b22-172">There can be any number of spaces between the GUID symbol and the literal payload, but no new lines.</span></span>  
  
```sql  
Guid'1afc7f5c-ffa0-4741-81cf-f12eAAb822bf'  
GUID  '1AFC7F5C-FFA0-4741-81CF-F12EAAB822BF'  
```  
  
## <a name="see-also"></a><span data-ttu-id="93b22-173">Vea también</span><span class="sxs-lookup"><span data-stu-id="93b22-173">See also</span></span>

- [<span data-ttu-id="93b22-174">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="93b22-174">Entity SQL Overview</span></span>](entity-sql-overview.md)
