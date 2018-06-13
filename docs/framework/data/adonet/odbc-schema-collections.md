---
title: Colecciones de esquemas de ODBC
ms.date: 03/30/2017
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
ms.openlocfilehash: 36d0859b897bfcea33803c219ade14722ed90421
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32766652"
---
# <a name="odbc-schema-collections"></a><span data-ttu-id="fad4c-102">Colecciones de esquemas de ODBC</span><span class="sxs-lookup"><span data-stu-id="fad4c-102">ODBC Schema Collections</span></span>
<span data-ttu-id="fad4c-103">En esta sección se describe la compatibilidad de las colecciones de esquemas con los controladores ODBC de Microsoft SQL Server, Oracle y Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="fad4c-103">This section discusses schema collection support for the ODBC drivers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-odbc-driver"></a><span data-ttu-id="fad4c-104">Controlador ODBC para Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="fad4c-104">Microsoft SQL Server ODBC Driver</span></span>  
 <span data-ttu-id="fad4c-105">El controlador ODBC de Microsoft SQL Server admite además las colecciones de esquemas comunes, las siguientes colecciones de esquemas específicas:</span><span class="sxs-lookup"><span data-stu-id="fad4c-105">The Microsoft SQL Server ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="fad4c-106">Tablas</span><span class="sxs-lookup"><span data-stu-id="fad4c-106">Tables</span></span>  
  
-   <span data-ttu-id="fad4c-107">Índices</span><span class="sxs-lookup"><span data-stu-id="fad4c-107">Indexes</span></span>  
  
-   <span data-ttu-id="fad4c-108">Columnas</span><span class="sxs-lookup"><span data-stu-id="fad4c-108">Columns</span></span>  
  
-   <span data-ttu-id="fad4c-109">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="fad4c-109">Procedures</span></span>  
  
-   <span data-ttu-id="fad4c-110">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="fad4c-110">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="fad4c-111">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="fad4c-111">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="fad4c-112">Vistas</span><span class="sxs-lookup"><span data-stu-id="fad4c-112">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="fad4c-113">Tablas y vistas</span><span class="sxs-lookup"><span data-stu-id="fad4c-113">Tables and Views</span></span>  
  
|<span data-ttu-id="fad4c-114">ColumName</span><span class="sxs-lookup"><span data-stu-id="fad4c-114">ColumnName</span></span>|<span data-ttu-id="fad4c-115">DataType</span><span class="sxs-lookup"><span data-stu-id="fad4c-115">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="fad4c-116">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="fad4c-116">TABLE_CAT</span></span>|<span data-ttu-id="fad4c-117">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-117">String</span></span>|  
|<span data-ttu-id="fad4c-118">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="fad4c-118">TABLE_SCHEM</span></span>|<span data-ttu-id="fad4c-119">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-119">String</span></span>|  
|<span data-ttu-id="fad4c-120">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="fad4c-120">TABLE_NAME</span></span>|<span data-ttu-id="fad4c-121">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-121">String</span></span>|  
|<span data-ttu-id="fad4c-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="fad4c-122">TABLE_TYPE</span></span>|<span data-ttu-id="fad4c-123">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-123">String</span></span>|  
|<span data-ttu-id="fad4c-124">REMARKS</span><span class="sxs-lookup"><span data-stu-id="fad4c-124">REMARKS</span></span>|<span data-ttu-id="fad4c-125">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-125">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="fad4c-126">Índices</span><span class="sxs-lookup"><span data-stu-id="fad4c-126">Indexes</span></span>  
  
|<span data-ttu-id="fad4c-127">ColumName</span><span class="sxs-lookup"><span data-stu-id="fad4c-127">ColumnName</span></span>|<span data-ttu-id="fad4c-128">DataType</span><span class="sxs-lookup"><span data-stu-id="fad4c-128">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="fad4c-129">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="fad4c-129">TABLE_CAT</span></span>|<span data-ttu-id="fad4c-130">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-130">String</span></span>|  
|<span data-ttu-id="fad4c-131">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="fad4c-131">TABLE_SCHEM</span></span>|<span data-ttu-id="fad4c-132">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-132">String</span></span>|  
|<span data-ttu-id="fad4c-133">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="fad4c-133">TABLE_NAME</span></span>|<span data-ttu-id="fad4c-134">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-134">String</span></span>|  
|<span data-ttu-id="fad4c-135">NON_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="fad4c-135">NON_UNIQUE</span></span>|<span data-ttu-id="fad4c-136">Int16</span><span class="sxs-lookup"><span data-stu-id="fad4c-136">Int16</span></span>|  
|<span data-ttu-id="fad4c-137">INDEX_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="fad4c-137">INDEX_QUALIFIER</span></span>|<span data-ttu-id="fad4c-138">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-138">String</span></span>|  
|<span data-ttu-id="fad4c-139">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="fad4c-139">INDEX_NAME</span></span>|<span data-ttu-id="fad4c-140">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-140">String</span></span>|  
|<span data-ttu-id="fad4c-141">TYPE</span><span class="sxs-lookup"><span data-stu-id="fad4c-141">TYPE</span></span>|<span data-ttu-id="fad4c-142">Int16</span><span class="sxs-lookup"><span data-stu-id="fad4c-142">Int16</span></span>|  
|<span data-ttu-id="fad4c-143">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="fad4c-143">ORDINAL_POSITION</span></span>|<span data-ttu-id="fad4c-144">Int16</span><span class="sxs-lookup"><span data-stu-id="fad4c-144">Int16</span></span>|  
|<span data-ttu-id="fad4c-145">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="fad4c-145">COLUMN_NAME</span></span>|<span data-ttu-id="fad4c-146">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-146">String</span></span>|  
|<span data-ttu-id="fad4c-147">ASC_OR_DESC</span><span class="sxs-lookup"><span data-stu-id="fad4c-147">ASC_OR_DESC</span></span>|<span data-ttu-id="fad4c-148">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-148">String</span></span>|  
|<span data-ttu-id="fad4c-149">CARDINATLITY</span><span class="sxs-lookup"><span data-stu-id="fad4c-149">CARDINATLITY</span></span>|<span data-ttu-id="fad4c-150">Int32</span><span class="sxs-lookup"><span data-stu-id="fad4c-150">Int32</span></span>|  
|<span data-ttu-id="fad4c-151">PAGES</span><span class="sxs-lookup"><span data-stu-id="fad4c-151">PAGES</span></span>|<span data-ttu-id="fad4c-152">Int32</span><span class="sxs-lookup"><span data-stu-id="fad4c-152">Int32</span></span>|  
|<span data-ttu-id="fad4c-153">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="fad4c-153">FILTER_CONDITION</span></span>|<span data-ttu-id="fad4c-154">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-154">String</span></span>|  
|<span data-ttu-id="fad4c-155">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fad4c-155">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="fad4c-156">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-156">String</span></span>|  
|<span data-ttu-id="fad4c-157">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="fad4c-157">SS_DATA_TYPE</span></span>|<span data-ttu-id="fad4c-158">Byte</span><span class="sxs-lookup"><span data-stu-id="fad4c-158">Byte</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="fad4c-159">Columnas</span><span class="sxs-lookup"><span data-stu-id="fad4c-159">Columns</span></span>  
  
|<span data-ttu-id="fad4c-160">ColumName</span><span class="sxs-lookup"><span data-stu-id="fad4c-160">ColumnName</span></span>|<span data-ttu-id="fad4c-161">DataType</span><span class="sxs-lookup"><span data-stu-id="fad4c-161">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="fad4c-162">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="fad4c-162">TABLE_CAT</span></span>|<span data-ttu-id="fad4c-163">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-163">String</span></span>|  
|<span data-ttu-id="fad4c-164">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="fad4c-164">TABLE_SCHEM</span></span>|<span data-ttu-id="fad4c-165">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-165">String</span></span>|  
|<span data-ttu-id="fad4c-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="fad4c-166">TABLE_NAME</span></span>|<span data-ttu-id="fad4c-167">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-167">String</span></span>|  
|<span data-ttu-id="fad4c-168">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="fad4c-168">COLUMN_NAME</span></span>|<span data-ttu-id="fad4c-169">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-169">String</span></span>|  
|<span data-ttu-id="fad4c-170">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="fad4c-170">DATA_TYPE</span></span>|<span data-ttu-id="fad4c-171">Int16</span><span class="sxs-lookup"><span data-stu-id="fad4c-171">Int16</span></span>|  
|<span data-ttu-id="fad4c-172">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="fad4c-172">TYPE_NAME</span></span>|<span data-ttu-id="fad4c-173">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-173">String</span></span>|  
|<span data-ttu-id="fad4c-174">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="fad4c-174">COLUMN_SIZE</span></span>|<span data-ttu-id="fad4c-175">Int32</span><span class="sxs-lookup"><span data-stu-id="fad4c-175">Int32</span></span>|  
|<span data-ttu-id="fad4c-176">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="fad4c-176">BUFFER_LENGTH</span></span>|<span data-ttu-id="fad4c-177">Int32</span><span class="sxs-lookup"><span data-stu-id="fad4c-177">Int32</span></span>|  
|<span data-ttu-id="fad4c-178">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="fad4c-178">DECIMAL_DIGITS</span></span>|<span data-ttu-id="fad4c-179">Int16</span><span class="sxs-lookup"><span data-stu-id="fad4c-179">Int16</span></span>|  
|<span data-ttu-id="fad4c-180">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="fad4c-180">NUM_PREC_RADIX</span></span>|<span data-ttu-id="fad4c-181">Int16</span><span class="sxs-lookup"><span data-stu-id="fad4c-181">Int16</span></span>|  
|<span data-ttu-id="fad4c-182">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="fad4c-182">NULLABLE</span></span>|<span data-ttu-id="fad4c-183">Int16</span><span class="sxs-lookup"><span data-stu-id="fad4c-183">Int16</span></span>|  
|<span data-ttu-id="fad4c-184">REMARKS</span><span class="sxs-lookup"><span data-stu-id="fad4c-184">REMARKS</span></span>|<span data-ttu-id="fad4c-185">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-185">String</span></span>|  
|<span data-ttu-id="fad4c-186">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="fad4c-186">COLUMN_DEF</span></span>|<span data-ttu-id="fad4c-187">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-187">String</span></span>|  
|<span data-ttu-id="fad4c-188">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="fad4c-188">SQL_DATA_TYPE</span></span>|<span data-ttu-id="fad4c-189">Int16</span><span class="sxs-lookup"><span data-stu-id="fad4c-189">Int16</span></span>|  
|<span data-ttu-id="fad4c-190">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="fad4c-190">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="fad4c-191">Int16</span><span class="sxs-lookup"><span data-stu-id="fad4c-191">Int16</span></span>|  
|<span data-ttu-id="fad4c-192">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="fad4c-192">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="fad4c-193">Int32</span><span class="sxs-lookup"><span data-stu-id="fad4c-193">Int32</span></span>|  
|<span data-ttu-id="fad4c-194">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="fad4c-194">ORDINAL_POSITION</span></span>|<span data-ttu-id="fad4c-195">Int32</span><span class="sxs-lookup"><span data-stu-id="fad4c-195">Int32</span></span>|  
|<span data-ttu-id="fad4c-196">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="fad4c-196">IS_NULLABLE</span></span>|<span data-ttu-id="fad4c-197">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-197">String</span></span>|  
|<span data-ttu-id="fad4c-198">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fad4c-198">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="fad4c-199">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-199">String</span></span>|  
|<span data-ttu-id="fad4c-200">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fad4c-200">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="fad4c-201">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-201">String</span></span>|  
|<span data-ttu-id="fad4c-202">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="fad4c-202">SS_DATA_TYPE</span></span>|<span data-ttu-id="fad4c-203">Byte</span><span class="sxs-lookup"><span data-stu-id="fad4c-203">Byte</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="fad4c-204">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="fad4c-204">Procedures</span></span>  
  
|<span data-ttu-id="fad4c-205">ColumName</span><span class="sxs-lookup"><span data-stu-id="fad4c-205">ColumnName</span></span>|<span data-ttu-id="fad4c-206">DataType</span><span class="sxs-lookup"><span data-stu-id="fad4c-206">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="fad4c-207">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="fad4c-207">PROCEDURE_CAT</span></span>|<span data-ttu-id="fad4c-208">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-208">String</span></span>|  
|<span data-ttu-id="fad4c-209">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="fad4c-209">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="fad4c-210">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-210">String</span></span>|  
|<span data-ttu-id="fad4c-211">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="fad4c-211">PROCEDURE_NAME</span></span>|<span data-ttu-id="fad4c-212">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-212">String</span></span>|  
|<span data-ttu-id="fad4c-213">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="fad4c-213">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="fad4c-214">Int32</span><span class="sxs-lookup"><span data-stu-id="fad4c-214">Int32</span></span>|  
|<span data-ttu-id="fad4c-215">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="fad4c-215">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="fad4c-216">Int32</span><span class="sxs-lookup"><span data-stu-id="fad4c-216">Int32</span></span>|  
|<span data-ttu-id="fad4c-217">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="fad4c-217">NUM_RESULT_SETS</span></span>|<span data-ttu-id="fad4c-218">Int32</span><span class="sxs-lookup"><span data-stu-id="fad4c-218">Int32</span></span>|  
|<span data-ttu-id="fad4c-219">REMARKS</span><span class="sxs-lookup"><span data-stu-id="fad4c-219">REMARKS</span></span>|<span data-ttu-id="fad4c-220">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-220">String</span></span>|  
|<span data-ttu-id="fad4c-221">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="fad4c-221">PROCEDURE_TYPE</span></span>|<span data-ttu-id="fad4c-222">Int16</span><span class="sxs-lookup"><span data-stu-id="fad4c-222">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="fad4c-223">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="fad4c-223">ProcedureColumns</span></span>  
  
|<span data-ttu-id="fad4c-224">ColumName</span><span class="sxs-lookup"><span data-stu-id="fad4c-224">ColumnName</span></span>|<span data-ttu-id="fad4c-225">DataType</span><span class="sxs-lookup"><span data-stu-id="fad4c-225">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="fad4c-226">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="fad4c-226">PROCEDURE_CAT</span></span>|<span data-ttu-id="fad4c-227">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-227">String</span></span>|  
|<span data-ttu-id="fad4c-228">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="fad4c-228">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="fad4c-229">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-229">String</span></span>|  
|<span data-ttu-id="fad4c-230">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="fad4c-230">PROCEDURE_NAME</span></span>|<span data-ttu-id="fad4c-231">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-231">String</span></span>|  
|<span data-ttu-id="fad4c-232">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="fad4c-232">COLUMN_NAME</span></span>|<span data-ttu-id="fad4c-233">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-233">String</span></span>|  
|<span data-ttu-id="fad4c-234">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="fad4c-234">COLUMN_TYPE</span></span>|<span data-ttu-id="fad4c-235">Int16</span><span class="sxs-lookup"><span data-stu-id="fad4c-235">Int16</span></span>|  
|<span data-ttu-id="fad4c-236">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="fad4c-236">DATA_TYPE</span></span>|<span data-ttu-id="fad4c-237">Int16</span><span class="sxs-lookup"><span data-stu-id="fad4c-237">Int16</span></span>|  
|<span data-ttu-id="fad4c-238">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="fad4c-238">TYPE_NAME</span></span>|<span data-ttu-id="fad4c-239">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-239">String</span></span>|  
|<span data-ttu-id="fad4c-240">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="fad4c-240">COLUMN_SIZE</span></span>|<span data-ttu-id="fad4c-241">Int32</span><span class="sxs-lookup"><span data-stu-id="fad4c-241">Int32</span></span>|  
|<span data-ttu-id="fad4c-242">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="fad4c-242">BUFFER_LENGTH</span></span>|<span data-ttu-id="fad4c-243">Int32</span><span class="sxs-lookup"><span data-stu-id="fad4c-243">Int32</span></span>|  
|<span data-ttu-id="fad4c-244">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="fad4c-244">DECIMAL_DIGITS</span></span>|<span data-ttu-id="fad4c-245">Int16</span><span class="sxs-lookup"><span data-stu-id="fad4c-245">Int16</span></span>|  
|<span data-ttu-id="fad4c-246">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="fad4c-246">NUM_PREC_RADIX</span></span>|<span data-ttu-id="fad4c-247">Int16</span><span class="sxs-lookup"><span data-stu-id="fad4c-247">Int16</span></span>|  
|<span data-ttu-id="fad4c-248">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="fad4c-248">NULLABLE</span></span>|<span data-ttu-id="fad4c-249">Int16</span><span class="sxs-lookup"><span data-stu-id="fad4c-249">Int16</span></span>|  
|<span data-ttu-id="fad4c-250">REMARKS</span><span class="sxs-lookup"><span data-stu-id="fad4c-250">REMARKS</span></span>|<span data-ttu-id="fad4c-251">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-251">String</span></span>|  
|<span data-ttu-id="fad4c-252">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="fad4c-252">COLUMN_DEF</span></span>|<span data-ttu-id="fad4c-253">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-253">String</span></span>|  
|<span data-ttu-id="fad4c-254">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="fad4c-254">SQL_DATA_TYPE</span></span>|<span data-ttu-id="fad4c-255">Int16</span><span class="sxs-lookup"><span data-stu-id="fad4c-255">Int16</span></span>|  
|<span data-ttu-id="fad4c-256">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="fad4c-256">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="fad4c-257">Int16</span><span class="sxs-lookup"><span data-stu-id="fad4c-257">Int16</span></span>|  
|<span data-ttu-id="fad4c-258">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="fad4c-258">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="fad4c-259">Int32</span><span class="sxs-lookup"><span data-stu-id="fad4c-259">Int32</span></span>|  
|<span data-ttu-id="fad4c-260">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="fad4c-260">ORDINAL_POSITION</span></span>|<span data-ttu-id="fad4c-261">Int32</span><span class="sxs-lookup"><span data-stu-id="fad4c-261">Int32</span></span>|  
|<span data-ttu-id="fad4c-262">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="fad4c-262">IS_NULLABLE</span></span>|<span data-ttu-id="fad4c-263">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-263">String</span></span>|  
|<span data-ttu-id="fad4c-264">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fad4c-264">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="fad4c-265">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-265">String</span></span>|  
|<span data-ttu-id="fad4c-266">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fad4c-266">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="fad4c-267">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-267">String</span></span>|  
|<span data-ttu-id="fad4c-268">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="fad4c-268">SS_DATA_TYPE</span></span>|<span data-ttu-id="fad4c-269">Byte</span><span class="sxs-lookup"><span data-stu-id="fad4c-269">Byte</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="fad4c-270">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="fad4c-270">ProcedureParameters</span></span>  
  
|<span data-ttu-id="fad4c-271">ColumName</span><span class="sxs-lookup"><span data-stu-id="fad4c-271">ColumnName</span></span>|<span data-ttu-id="fad4c-272">DataType</span><span class="sxs-lookup"><span data-stu-id="fad4c-272">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="fad4c-273">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="fad4c-273">PROCEDURE_CAT</span></span>|<span data-ttu-id="fad4c-274">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-274">String</span></span>|  
|<span data-ttu-id="fad4c-275">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="fad4c-275">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="fad4c-276">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-276">String</span></span>|  
|<span data-ttu-id="fad4c-277">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="fad4c-277">PROCEDURE_NAME</span></span>|<span data-ttu-id="fad4c-278">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-278">String</span></span>|  
|<span data-ttu-id="fad4c-279">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="fad4c-279">COLUMN_NAME</span></span>|<span data-ttu-id="fad4c-280">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-280">String</span></span>|  
|<span data-ttu-id="fad4c-281">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="fad4c-281">COLUMN_TYPE</span></span>|<span data-ttu-id="fad4c-282">Int16</span><span class="sxs-lookup"><span data-stu-id="fad4c-282">Int16</span></span>|  
|<span data-ttu-id="fad4c-283">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="fad4c-283">DATA_TYPE</span></span>|<span data-ttu-id="fad4c-284">Int16</span><span class="sxs-lookup"><span data-stu-id="fad4c-284">Int16</span></span>|  
|<span data-ttu-id="fad4c-285">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="fad4c-285">TYPE_NAME</span></span>|<span data-ttu-id="fad4c-286">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-286">String</span></span>|  
|<span data-ttu-id="fad4c-287">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="fad4c-287">COLUMN_SIZE</span></span>|<span data-ttu-id="fad4c-288">Int32</span><span class="sxs-lookup"><span data-stu-id="fad4c-288">Int32</span></span>|  
|<span data-ttu-id="fad4c-289">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="fad4c-289">BUFFER_LENGTH</span></span>|<span data-ttu-id="fad4c-290">Int32</span><span class="sxs-lookup"><span data-stu-id="fad4c-290">Int32</span></span>|  
|<span data-ttu-id="fad4c-291">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="fad4c-291">DECIMAL_DIGITS</span></span>|<span data-ttu-id="fad4c-292">Int16</span><span class="sxs-lookup"><span data-stu-id="fad4c-292">Int16</span></span>|  
|<span data-ttu-id="fad4c-293">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="fad4c-293">NUM_PREC_RADIX</span></span>|<span data-ttu-id="fad4c-294">Int16</span><span class="sxs-lookup"><span data-stu-id="fad4c-294">Int16</span></span>|  
|<span data-ttu-id="fad4c-295">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="fad4c-295">NULLABLE</span></span>|<span data-ttu-id="fad4c-296">Int16</span><span class="sxs-lookup"><span data-stu-id="fad4c-296">Int16</span></span>|  
|<span data-ttu-id="fad4c-297">REMARKS</span><span class="sxs-lookup"><span data-stu-id="fad4c-297">REMARKS</span></span>|<span data-ttu-id="fad4c-298">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-298">String</span></span>|  
|<span data-ttu-id="fad4c-299">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="fad4c-299">COLUMN_DEF</span></span>|<span data-ttu-id="fad4c-300">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-300">String</span></span>|  
|<span data-ttu-id="fad4c-301">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="fad4c-301">SQL_DATA_TYPE</span></span>|<span data-ttu-id="fad4c-302">Int16</span><span class="sxs-lookup"><span data-stu-id="fad4c-302">Int16</span></span>|  
|<span data-ttu-id="fad4c-303">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="fad4c-303">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="fad4c-304">Int16</span><span class="sxs-lookup"><span data-stu-id="fad4c-304">Int16</span></span>|  
|<span data-ttu-id="fad4c-305">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="fad4c-305">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="fad4c-306">Int32</span><span class="sxs-lookup"><span data-stu-id="fad4c-306">Int32</span></span>|  
|<span data-ttu-id="fad4c-307">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="fad4c-307">ORDINAL_POSITION</span></span>|<span data-ttu-id="fad4c-308">Int32</span><span class="sxs-lookup"><span data-stu-id="fad4c-308">Int32</span></span>|  
|<span data-ttu-id="fad4c-309">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="fad4c-309">IS_NULLABLE</span></span>|<span data-ttu-id="fad4c-310">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-310">String</span></span>|  
|<span data-ttu-id="fad4c-311">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fad4c-311">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="fad4c-312">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-312">String</span></span>|  
|<span data-ttu-id="fad4c-313">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fad4c-313">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="fad4c-314">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-314">String</span></span>|  
|<span data-ttu-id="fad4c-315">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="fad4c-315">SS_DATA_TYPE</span></span>|<span data-ttu-id="fad4c-316">Byte</span><span class="sxs-lookup"><span data-stu-id="fad4c-316">Byte</span></span>|  
  
## <a name="microsoft-oracle-odbc-driver"></a><span data-ttu-id="fad4c-317">Controlador ODBC para Oracle de Microsoft</span><span class="sxs-lookup"><span data-stu-id="fad4c-317">Microsoft Oracle ODBC Driver</span></span>  
 <span data-ttu-id="fad4c-318">El controlador ODBC de Oracle de Microsoft SQL Server admite además las colecciones de esquemas comunes, las siguientes colecciones de esquemas específicas:</span><span class="sxs-lookup"><span data-stu-id="fad4c-318">The Microsoft SQL Server Oracle ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="fad4c-319">Tablas</span><span class="sxs-lookup"><span data-stu-id="fad4c-319">Tables</span></span>  
  
-   <span data-ttu-id="fad4c-320">Columnas</span><span class="sxs-lookup"><span data-stu-id="fad4c-320">Columns</span></span>  
  
-   <span data-ttu-id="fad4c-321">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="fad4c-321">Procedures</span></span>  
  
-   <span data-ttu-id="fad4c-322">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="fad4c-322">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="fad4c-323">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="fad4c-323">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="fad4c-324">Vistas</span><span class="sxs-lookup"><span data-stu-id="fad4c-324">Views</span></span>  
  
-   <span data-ttu-id="fad4c-325">Índices</span><span class="sxs-lookup"><span data-stu-id="fad4c-325">Indexes</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="fad4c-326">Tablas y vistas</span><span class="sxs-lookup"><span data-stu-id="fad4c-326">Tables and Views</span></span>  
  
|<span data-ttu-id="fad4c-327">ColumName</span><span class="sxs-lookup"><span data-stu-id="fad4c-327">ColumnName</span></span>|<span data-ttu-id="fad4c-328">DataType</span><span class="sxs-lookup"><span data-stu-id="fad4c-328">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="fad4c-329">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="fad4c-329">TABLE_QUALIFIER</span></span>|<span data-ttu-id="fad4c-330">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-330">String</span></span>|  
|<span data-ttu-id="fad4c-331">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="fad4c-331">TABLE_OWNER</span></span>|<span data-ttu-id="fad4c-332">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-332">String</span></span>|  
|<span data-ttu-id="fad4c-333">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="fad4c-333">TABLE_NAME</span></span>|<span data-ttu-id="fad4c-334">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-334">String</span></span>|  
|<span data-ttu-id="fad4c-335">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="fad4c-335">TABLE_TYPE</span></span>|<span data-ttu-id="fad4c-336">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-336">String</span></span>|  
|<span data-ttu-id="fad4c-337">REMARKS</span><span class="sxs-lookup"><span data-stu-id="fad4c-337">REMARKS</span></span>|<span data-ttu-id="fad4c-338">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-338">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="fad4c-339">Columnas</span><span class="sxs-lookup"><span data-stu-id="fad4c-339">Columns</span></span>  
  
|<span data-ttu-id="fad4c-340">ColumName</span><span class="sxs-lookup"><span data-stu-id="fad4c-340">ColumnName</span></span>|<span data-ttu-id="fad4c-341">DataType</span><span class="sxs-lookup"><span data-stu-id="fad4c-341">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="fad4c-342">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="fad4c-342">TABLE_QUALIFIER</span></span>|<span data-ttu-id="fad4c-343">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-343">String</span></span>|  
|<span data-ttu-id="fad4c-344">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="fad4c-344">TABLE_OWNER</span></span>|<span data-ttu-id="fad4c-345">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-345">String</span></span>|  
|<span data-ttu-id="fad4c-346">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="fad4c-346">TABLE_NAME</span></span>|<span data-ttu-id="fad4c-347">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-347">String</span></span>|  
|<span data-ttu-id="fad4c-348">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="fad4c-348">COLUMN_NAME</span></span>|<span data-ttu-id="fad4c-349">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-349">String</span></span>|  
|<span data-ttu-id="fad4c-350">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="fad4c-350">DATA_TYPE</span></span>|<span data-ttu-id="fad4c-351">Int16</span><span class="sxs-lookup"><span data-stu-id="fad4c-351">Int16</span></span>|  
|<span data-ttu-id="fad4c-352">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="fad4c-352">TYPE_NAME</span></span>|<span data-ttu-id="fad4c-353">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-353">String</span></span>|  
|<span data-ttu-id="fad4c-354">PRECISION</span><span class="sxs-lookup"><span data-stu-id="fad4c-354">PRECISION</span></span>|<span data-ttu-id="fad4c-355">Int32</span><span class="sxs-lookup"><span data-stu-id="fad4c-355">Int32</span></span>|  
|<span data-ttu-id="fad4c-356">LENGTH</span><span class="sxs-lookup"><span data-stu-id="fad4c-356">LENGTH</span></span>|<span data-ttu-id="fad4c-357">Int32</span><span class="sxs-lookup"><span data-stu-id="fad4c-357">Int32</span></span>|  
|<span data-ttu-id="fad4c-358">SCALE</span><span class="sxs-lookup"><span data-stu-id="fad4c-358">SCALE</span></span>|<span data-ttu-id="fad4c-359">Int16</span><span class="sxs-lookup"><span data-stu-id="fad4c-359">Int16</span></span>|  
|<span data-ttu-id="fad4c-360">RADIX</span><span class="sxs-lookup"><span data-stu-id="fad4c-360">RADIX</span></span>|<span data-ttu-id="fad4c-361">Int16</span><span class="sxs-lookup"><span data-stu-id="fad4c-361">Int16</span></span>|  
|<span data-ttu-id="fad4c-362">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="fad4c-362">NULLABLE</span></span>|<span data-ttu-id="fad4c-363">Int16</span><span class="sxs-lookup"><span data-stu-id="fad4c-363">Int16</span></span>|  
|<span data-ttu-id="fad4c-364">REMARKS</span><span class="sxs-lookup"><span data-stu-id="fad4c-364">REMARKS</span></span>|<span data-ttu-id="fad4c-365">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-365">String</span></span>|  
|<span data-ttu-id="fad4c-366">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="fad4c-366">ORDINAL_POSITION</span></span>|<span data-ttu-id="fad4c-367">Int32</span><span class="sxs-lookup"><span data-stu-id="fad4c-367">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="fad4c-368">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="fad4c-368">Procedures</span></span>  
  
|<span data-ttu-id="fad4c-369">ColumName</span><span class="sxs-lookup"><span data-stu-id="fad4c-369">ColumnName</span></span>|<span data-ttu-id="fad4c-370">DataType</span><span class="sxs-lookup"><span data-stu-id="fad4c-370">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="fad4c-371">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="fad4c-371">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="fad4c-372">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-372">String</span></span>|  
|<span data-ttu-id="fad4c-373">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="fad4c-373">PROCEDURE_OWNER</span></span>|<span data-ttu-id="fad4c-374">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-374">String</span></span>|  
|<span data-ttu-id="fad4c-375">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="fad4c-375">PROCEDURE_NAME</span></span>|<span data-ttu-id="fad4c-376">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-376">String</span></span>|  
|<span data-ttu-id="fad4c-377">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="fad4c-377">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="fad4c-378">Int16</span><span class="sxs-lookup"><span data-stu-id="fad4c-378">Int16</span></span>|  
|<span data-ttu-id="fad4c-379">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="fad4c-379">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="fad4c-380">Int16</span><span class="sxs-lookup"><span data-stu-id="fad4c-380">Int16</span></span>|  
|<span data-ttu-id="fad4c-381">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="fad4c-381">NUM_RESULT_SETS</span></span>|<span data-ttu-id="fad4c-382">Int16</span><span class="sxs-lookup"><span data-stu-id="fad4c-382">Int16</span></span>|  
|<span data-ttu-id="fad4c-383">REMARKS</span><span class="sxs-lookup"><span data-stu-id="fad4c-383">REMARKS</span></span>|<span data-ttu-id="fad4c-384">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-384">String</span></span>|  
|<span data-ttu-id="fad4c-385">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="fad4c-385">PROCEDURE_TYPE</span></span>|<span data-ttu-id="fad4c-386">Int16</span><span class="sxs-lookup"><span data-stu-id="fad4c-386">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="fad4c-387">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="fad4c-387">ProcedureColumns</span></span>  
  
|<span data-ttu-id="fad4c-388">ColumName</span><span class="sxs-lookup"><span data-stu-id="fad4c-388">ColumnName</span></span>|<span data-ttu-id="fad4c-389">DataType</span><span class="sxs-lookup"><span data-stu-id="fad4c-389">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="fad4c-390">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="fad4c-390">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="fad4c-391">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-391">String</span></span>|  
|<span data-ttu-id="fad4c-392">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="fad4c-392">PROCEDURE_OWNER</span></span>|<span data-ttu-id="fad4c-393">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-393">String</span></span>|  
|<span data-ttu-id="fad4c-394">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="fad4c-394">PROCEDURE_NAME</span></span>|<span data-ttu-id="fad4c-395">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-395">String</span></span>|  
|<span data-ttu-id="fad4c-396">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="fad4c-396">COLUMN_NAME</span></span>|<span data-ttu-id="fad4c-397">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-397">String</span></span>|  
|<span data-ttu-id="fad4c-398">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="fad4c-398">COLUMN_TYPE</span></span>|<span data-ttu-id="fad4c-399">Int16</span><span class="sxs-lookup"><span data-stu-id="fad4c-399">Int16</span></span>|  
|<span data-ttu-id="fad4c-400">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="fad4c-400">DATA_TYPE</span></span>|<span data-ttu-id="fad4c-401">Int16</span><span class="sxs-lookup"><span data-stu-id="fad4c-401">Int16</span></span>|  
|<span data-ttu-id="fad4c-402">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="fad4c-402">TYPE_NAME</span></span>|<span data-ttu-id="fad4c-403">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-403">String</span></span>|  
|<span data-ttu-id="fad4c-404">PRECISION</span><span class="sxs-lookup"><span data-stu-id="fad4c-404">PRECISION</span></span>|<span data-ttu-id="fad4c-405">Int32</span><span class="sxs-lookup"><span data-stu-id="fad4c-405">Int32</span></span>|  
|<span data-ttu-id="fad4c-406">LENGTH</span><span class="sxs-lookup"><span data-stu-id="fad4c-406">LENGTH</span></span>|<span data-ttu-id="fad4c-407">Int32</span><span class="sxs-lookup"><span data-stu-id="fad4c-407">Int32</span></span>|  
|<span data-ttu-id="fad4c-408">SCALE</span><span class="sxs-lookup"><span data-stu-id="fad4c-408">SCALE</span></span>|<span data-ttu-id="fad4c-409">Int16</span><span class="sxs-lookup"><span data-stu-id="fad4c-409">Int16</span></span>|  
|<span data-ttu-id="fad4c-410">RADIX</span><span class="sxs-lookup"><span data-stu-id="fad4c-410">RADIX</span></span>|<span data-ttu-id="fad4c-411">Int16</span><span class="sxs-lookup"><span data-stu-id="fad4c-411">Int16</span></span>|  
|<span data-ttu-id="fad4c-412">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="fad4c-412">NULLABLE</span></span>|<span data-ttu-id="fad4c-413">Int16</span><span class="sxs-lookup"><span data-stu-id="fad4c-413">Int16</span></span>|  
|<span data-ttu-id="fad4c-414">REMARKS</span><span class="sxs-lookup"><span data-stu-id="fad4c-414">REMARKS</span></span>|<span data-ttu-id="fad4c-415">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-415">String</span></span>|  
|<span data-ttu-id="fad4c-416">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="fad4c-416">OVERLOAD</span></span>|<span data-ttu-id="fad4c-417">Int32</span><span class="sxs-lookup"><span data-stu-id="fad4c-417">Int32</span></span>|  
|<span data-ttu-id="fad4c-418">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="fad4c-418">ORDINAL_POSITION</span></span>|<span data-ttu-id="fad4c-419">Int32</span><span class="sxs-lookup"><span data-stu-id="fad4c-419">Int32</span></span>|  
  
## <a name="microsoft-jet-odbc-driver"></a><span data-ttu-id="fad4c-420">Controlador ODBC de Microsoft para Jet</span><span class="sxs-lookup"><span data-stu-id="fad4c-420">Microsoft Jet ODBC Driver</span></span>  
 <span data-ttu-id="fad4c-421">El controlador ODBC de Microsoft para Jet admite, además de las colecciones de esquemas comunes, las siguientes colecciones de esquemas específicas:</span><span class="sxs-lookup"><span data-stu-id="fad4c-421">The Microsoft Jet ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="fad4c-422">Tablas</span><span class="sxs-lookup"><span data-stu-id="fad4c-422">Tables</span></span>  
  
-   <span data-ttu-id="fad4c-423">Índices</span><span class="sxs-lookup"><span data-stu-id="fad4c-423">Indexes</span></span>  
  
-   <span data-ttu-id="fad4c-424">Columnas</span><span class="sxs-lookup"><span data-stu-id="fad4c-424">Columns</span></span>  
  
-   <span data-ttu-id="fad4c-425">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="fad4c-425">Procedures</span></span>  
  
-   <span data-ttu-id="fad4c-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="fad4c-426">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="fad4c-427">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="fad4c-427">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="fad4c-428">Vistas</span><span class="sxs-lookup"><span data-stu-id="fad4c-428">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="fad4c-429">Tablas y vistas</span><span class="sxs-lookup"><span data-stu-id="fad4c-429">Tables and Views</span></span>  
  
|<span data-ttu-id="fad4c-430">ColumName</span><span class="sxs-lookup"><span data-stu-id="fad4c-430">ColumnName</span></span>|<span data-ttu-id="fad4c-431">DataType</span><span class="sxs-lookup"><span data-stu-id="fad4c-431">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="fad4c-432">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="fad4c-432">TABLE_QUALIFIER</span></span>|<span data-ttu-id="fad4c-433">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-433">String</span></span>|  
|<span data-ttu-id="fad4c-434">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="fad4c-434">TABLE_OWNER</span></span>|<span data-ttu-id="fad4c-435">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-435">String</span></span>|  
|<span data-ttu-id="fad4c-436">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="fad4c-436">TABLE_NAME</span></span>|<span data-ttu-id="fad4c-437">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-437">String</span></span>|  
|<span data-ttu-id="fad4c-438">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="fad4c-438">TABLE_TYPE</span></span>|<span data-ttu-id="fad4c-439">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-439">String</span></span>|  
|<span data-ttu-id="fad4c-440">REMARKS</span><span class="sxs-lookup"><span data-stu-id="fad4c-440">REMARKS</span></span>|<span data-ttu-id="fad4c-441">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-441">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="fad4c-442">Columnas</span><span class="sxs-lookup"><span data-stu-id="fad4c-442">Columns</span></span>  
  
|<span data-ttu-id="fad4c-443">ColumName</span><span class="sxs-lookup"><span data-stu-id="fad4c-443">ColumnName</span></span>|<span data-ttu-id="fad4c-444">DataType</span><span class="sxs-lookup"><span data-stu-id="fad4c-444">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="fad4c-445">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="fad4c-445">TABLE_QUALIFIER</span></span>|<span data-ttu-id="fad4c-446">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-446">String</span></span>|  
|<span data-ttu-id="fad4c-447">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="fad4c-447">TABLE_OWNER</span></span>|<span data-ttu-id="fad4c-448">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-448">String</span></span>|  
|<span data-ttu-id="fad4c-449">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="fad4c-449">TABLE_NAME</span></span>|<span data-ttu-id="fad4c-450">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-450">String</span></span>|  
|<span data-ttu-id="fad4c-451">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="fad4c-451">COLUMN_NAME</span></span>|<span data-ttu-id="fad4c-452">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-452">String</span></span>|  
|<span data-ttu-id="fad4c-453">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="fad4c-453">DATA_TYPE</span></span>|<span data-ttu-id="fad4c-454">Int16</span><span class="sxs-lookup"><span data-stu-id="fad4c-454">Int16</span></span>|  
|<span data-ttu-id="fad4c-455">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="fad4c-455">TYPE_NAME</span></span>|<span data-ttu-id="fad4c-456">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-456">String</span></span>|  
|<span data-ttu-id="fad4c-457">PRECISION</span><span class="sxs-lookup"><span data-stu-id="fad4c-457">PRECISION</span></span>|<span data-ttu-id="fad4c-458">Int32</span><span class="sxs-lookup"><span data-stu-id="fad4c-458">Int32</span></span>|  
|<span data-ttu-id="fad4c-459">LENGTH</span><span class="sxs-lookup"><span data-stu-id="fad4c-459">LENGTH</span></span>|<span data-ttu-id="fad4c-460">Int32</span><span class="sxs-lookup"><span data-stu-id="fad4c-460">Int32</span></span>|  
|<span data-ttu-id="fad4c-461">SCALE</span><span class="sxs-lookup"><span data-stu-id="fad4c-461">SCALE</span></span>|<span data-ttu-id="fad4c-462">Int16</span><span class="sxs-lookup"><span data-stu-id="fad4c-462">Int16</span></span>|  
|<span data-ttu-id="fad4c-463">RADIX</span><span class="sxs-lookup"><span data-stu-id="fad4c-463">RADIX</span></span>|<span data-ttu-id="fad4c-464">Int16</span><span class="sxs-lookup"><span data-stu-id="fad4c-464">Int16</span></span>|  
|<span data-ttu-id="fad4c-465">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="fad4c-465">NULLABLE</span></span>|<span data-ttu-id="fad4c-466">Int16</span><span class="sxs-lookup"><span data-stu-id="fad4c-466">Int16</span></span>|  
|<span data-ttu-id="fad4c-467">REMARKS</span><span class="sxs-lookup"><span data-stu-id="fad4c-467">REMARKS</span></span>|<span data-ttu-id="fad4c-468">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-468">String</span></span>|  
|<span data-ttu-id="fad4c-469">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="fad4c-469">ORDINAL_POSITION</span></span>|<span data-ttu-id="fad4c-470">Int32</span><span class="sxs-lookup"><span data-stu-id="fad4c-470">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="fad4c-471">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="fad4c-471">Procedures</span></span>  
  
|<span data-ttu-id="fad4c-472">ColumName</span><span class="sxs-lookup"><span data-stu-id="fad4c-472">ColumnName</span></span>|<span data-ttu-id="fad4c-473">DataType</span><span class="sxs-lookup"><span data-stu-id="fad4c-473">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="fad4c-474">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="fad4c-474">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="fad4c-475">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-475">String</span></span>|  
|<span data-ttu-id="fad4c-476">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="fad4c-476">PROCEDURE_OWNER</span></span>|<span data-ttu-id="fad4c-477">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-477">String</span></span>|  
|<span data-ttu-id="fad4c-478">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="fad4c-478">PROCEDURE_NAME</span></span>|<span data-ttu-id="fad4c-479">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-479">String</span></span>|  
|<span data-ttu-id="fad4c-480">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="fad4c-480">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="fad4c-481">Int16</span><span class="sxs-lookup"><span data-stu-id="fad4c-481">Int16</span></span>|  
|<span data-ttu-id="fad4c-482">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="fad4c-482">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="fad4c-483">Int16</span><span class="sxs-lookup"><span data-stu-id="fad4c-483">Int16</span></span>|  
|<span data-ttu-id="fad4c-484">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="fad4c-484">NUM_RESULT_SETS</span></span>|<span data-ttu-id="fad4c-485">Int16</span><span class="sxs-lookup"><span data-stu-id="fad4c-485">Int16</span></span>|  
|<span data-ttu-id="fad4c-486">REMARKS</span><span class="sxs-lookup"><span data-stu-id="fad4c-486">REMARKS</span></span>|<span data-ttu-id="fad4c-487">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-487">String</span></span>|  
|<span data-ttu-id="fad4c-488">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="fad4c-488">PROCEDURE_TYPE</span></span>|<span data-ttu-id="fad4c-489">Int16</span><span class="sxs-lookup"><span data-stu-id="fad4c-489">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="fad4c-490">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="fad4c-490">ProcedureColumns</span></span>  
  
|<span data-ttu-id="fad4c-491">ColumName</span><span class="sxs-lookup"><span data-stu-id="fad4c-491">ColumnName</span></span>|<span data-ttu-id="fad4c-492">DataType</span><span class="sxs-lookup"><span data-stu-id="fad4c-492">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="fad4c-493">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="fad4c-493">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="fad4c-494">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-494">String</span></span>|  
|<span data-ttu-id="fad4c-495">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="fad4c-495">PROCEDURE_OWNER</span></span>|<span data-ttu-id="fad4c-496">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-496">String</span></span>|  
|<span data-ttu-id="fad4c-497">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="fad4c-497">PROCEDURE_NAME</span></span>|<span data-ttu-id="fad4c-498">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-498">String</span></span>|  
|<span data-ttu-id="fad4c-499">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="fad4c-499">COLUMN_NAME</span></span>|<span data-ttu-id="fad4c-500">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-500">String</span></span>|  
|<span data-ttu-id="fad4c-501">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="fad4c-501">COLUMN_TYPE</span></span>|<span data-ttu-id="fad4c-502">Int16</span><span class="sxs-lookup"><span data-stu-id="fad4c-502">Int16</span></span>|  
|<span data-ttu-id="fad4c-503">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="fad4c-503">DATA_TYPE</span></span>|<span data-ttu-id="fad4c-504">Int16</span><span class="sxs-lookup"><span data-stu-id="fad4c-504">Int16</span></span>|  
|<span data-ttu-id="fad4c-505">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="fad4c-505">TYPE_NAME</span></span>|<span data-ttu-id="fad4c-506">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-506">String</span></span>|  
|<span data-ttu-id="fad4c-507">PRECISION</span><span class="sxs-lookup"><span data-stu-id="fad4c-507">PRECISION</span></span>|<span data-ttu-id="fad4c-508">Int32</span><span class="sxs-lookup"><span data-stu-id="fad4c-508">Int32</span></span>|  
|<span data-ttu-id="fad4c-509">LENGTH</span><span class="sxs-lookup"><span data-stu-id="fad4c-509">LENGTH</span></span>|<span data-ttu-id="fad4c-510">Int32</span><span class="sxs-lookup"><span data-stu-id="fad4c-510">Int32</span></span>|  
|<span data-ttu-id="fad4c-511">SCALE</span><span class="sxs-lookup"><span data-stu-id="fad4c-511">SCALE</span></span>|<span data-ttu-id="fad4c-512">Int16</span><span class="sxs-lookup"><span data-stu-id="fad4c-512">Int16</span></span>|  
|<span data-ttu-id="fad4c-513">RADIX</span><span class="sxs-lookup"><span data-stu-id="fad4c-513">RADIX</span></span>|<span data-ttu-id="fad4c-514">Int16</span><span class="sxs-lookup"><span data-stu-id="fad4c-514">Int16</span></span>|  
|<span data-ttu-id="fad4c-515">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="fad4c-515">NULLABLE</span></span>|<span data-ttu-id="fad4c-516">Int16</span><span class="sxs-lookup"><span data-stu-id="fad4c-516">Int16</span></span>|  
|<span data-ttu-id="fad4c-517">REMARKS</span><span class="sxs-lookup"><span data-stu-id="fad4c-517">REMARKS</span></span>|<span data-ttu-id="fad4c-518">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-518">String</span></span>|  
|<span data-ttu-id="fad4c-519">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="fad4c-519">OVERLOAD</span></span>|<span data-ttu-id="fad4c-520">Int32</span><span class="sxs-lookup"><span data-stu-id="fad4c-520">Int32</span></span>|  
|<span data-ttu-id="fad4c-521">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="fad4c-521">ORDINAL_POSITION</span></span>|<span data-ttu-id="fad4c-522">Int32</span><span class="sxs-lookup"><span data-stu-id="fad4c-522">Int32</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="fad4c-523">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="fad4c-523">ProcedureParameters</span></span>  
  
|<span data-ttu-id="fad4c-524">ColumName</span><span class="sxs-lookup"><span data-stu-id="fad4c-524">ColumnName</span></span>|<span data-ttu-id="fad4c-525">DataType</span><span class="sxs-lookup"><span data-stu-id="fad4c-525">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="fad4c-526">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="fad4c-526">PROCEDURE_CAT</span></span>|<span data-ttu-id="fad4c-527">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-527">String</span></span>|  
|<span data-ttu-id="fad4c-528">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="fad4c-528">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="fad4c-529">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-529">String</span></span>|  
|<span data-ttu-id="fad4c-530">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="fad4c-530">PROCEDURE_NAME</span></span>|<span data-ttu-id="fad4c-531">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-531">String</span></span>|  
|<span data-ttu-id="fad4c-532">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="fad4c-532">COLUMN_NAME</span></span>|<span data-ttu-id="fad4c-533">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-533">String</span></span>|  
|<span data-ttu-id="fad4c-534">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="fad4c-534">COLUMN_TYPE</span></span>|<span data-ttu-id="fad4c-535">Int16</span><span class="sxs-lookup"><span data-stu-id="fad4c-535">Int16</span></span>|  
|<span data-ttu-id="fad4c-536">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="fad4c-536">DATA_TYPE</span></span>|<span data-ttu-id="fad4c-537">Int16</span><span class="sxs-lookup"><span data-stu-id="fad4c-537">Int16</span></span>|  
|<span data-ttu-id="fad4c-538">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="fad4c-538">TYPE_NAME</span></span>|<span data-ttu-id="fad4c-539">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-539">String</span></span>|  
|<span data-ttu-id="fad4c-540">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="fad4c-540">COLUMN_SIZE</span></span>|<span data-ttu-id="fad4c-541">Int32</span><span class="sxs-lookup"><span data-stu-id="fad4c-541">Int32</span></span>|  
|<span data-ttu-id="fad4c-542">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="fad4c-542">BUFFER_LENGTH</span></span>|<span data-ttu-id="fad4c-543">Int32</span><span class="sxs-lookup"><span data-stu-id="fad4c-543">Int32</span></span>|  
|<span data-ttu-id="fad4c-544">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="fad4c-544">DECIMAL_DIGITS</span></span>|<span data-ttu-id="fad4c-545">Int16</span><span class="sxs-lookup"><span data-stu-id="fad4c-545">Int16</span></span>|  
|<span data-ttu-id="fad4c-546">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="fad4c-546">NUM_PREC_RADIX</span></span>|<span data-ttu-id="fad4c-547">Int16</span><span class="sxs-lookup"><span data-stu-id="fad4c-547">Int16</span></span>|  
|<span data-ttu-id="fad4c-548">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="fad4c-548">NULLABLE</span></span>|<span data-ttu-id="fad4c-549">Int16</span><span class="sxs-lookup"><span data-stu-id="fad4c-549">Int16</span></span>|  
|<span data-ttu-id="fad4c-550">REMARKS</span><span class="sxs-lookup"><span data-stu-id="fad4c-550">REMARKS</span></span>|<span data-ttu-id="fad4c-551">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-551">String</span></span>|  
|<span data-ttu-id="fad4c-552">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="fad4c-552">COLUMN_DEF</span></span>|<span data-ttu-id="fad4c-553">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-553">String</span></span>|  
|<span data-ttu-id="fad4c-554">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="fad4c-554">SQL_DATA_TYPE</span></span>|<span data-ttu-id="fad4c-555">Int16</span><span class="sxs-lookup"><span data-stu-id="fad4c-555">Int16</span></span>|  
|<span data-ttu-id="fad4c-556">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="fad4c-556">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="fad4c-557">Int16</span><span class="sxs-lookup"><span data-stu-id="fad4c-557">Int16</span></span>|  
|<span data-ttu-id="fad4c-558">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="fad4c-558">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="fad4c-559">Int32</span><span class="sxs-lookup"><span data-stu-id="fad4c-559">Int32</span></span>|  
|<span data-ttu-id="fad4c-560">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="fad4c-560">ORDINAL_POSITION</span></span>|<span data-ttu-id="fad4c-561">Int32</span><span class="sxs-lookup"><span data-stu-id="fad4c-561">Int32</span></span>|  
|<span data-ttu-id="fad4c-562">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="fad4c-562">IS_NULLABLE</span></span>|<span data-ttu-id="fad4c-563">String</span><span class="sxs-lookup"><span data-stu-id="fad4c-563">String</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fad4c-564">Vea también</span><span class="sxs-lookup"><span data-stu-id="fad4c-564">See Also</span></span>  
 [<span data-ttu-id="fad4c-565">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="fad4c-565">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
