---
title: Colecciones de esquemas de ODBC
ms.date: 03/30/2017
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
ms.openlocfilehash: ffe80120ceffbe29c0a117cf1194860c5782be8c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57365911"
---
# <a name="odbc-schema-collections"></a><span data-ttu-id="7498c-102">Colecciones de esquemas de ODBC</span><span class="sxs-lookup"><span data-stu-id="7498c-102">ODBC Schema Collections</span></span>

<span data-ttu-id="7498c-103">En esta sección se describe la compatibilidad de las colecciones de esquemas con los controladores ODBC de Microsoft SQL Server, Oracle y Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="7498c-103">This section discusses schema collection support for the ODBC drivers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>

## <a name="microsoft-sql-server-odbc-driver"></a><span data-ttu-id="7498c-104">Controlador ODBC para Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="7498c-104">Microsoft SQL Server ODBC Driver</span></span>

<span data-ttu-id="7498c-105">El controlador ODBC de Microsoft SQL Server admite las siguientes colecciones de esquemas específicas además de las colecciones de esquemas comunes:</span><span class="sxs-lookup"><span data-stu-id="7498c-105">The Microsoft SQL Server ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="7498c-106">Tablas</span><span class="sxs-lookup"><span data-stu-id="7498c-106">Tables</span></span>

- <span data-ttu-id="7498c-107">Índices</span><span class="sxs-lookup"><span data-stu-id="7498c-107">Indexes</span></span>

- <span data-ttu-id="7498c-108">Columnas</span><span class="sxs-lookup"><span data-stu-id="7498c-108">Columns</span></span>

- <span data-ttu-id="7498c-109">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="7498c-109">Procedures</span></span>

- <span data-ttu-id="7498c-110">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="7498c-110">ProcedureColumns</span></span>

- <span data-ttu-id="7498c-111">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="7498c-111">ProcedureParameters</span></span>

- <span data-ttu-id="7498c-112">Vistas</span><span class="sxs-lookup"><span data-stu-id="7498c-112">Views</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="7498c-113">Tablas y vistas</span><span class="sxs-lookup"><span data-stu-id="7498c-113">Tables and Views</span></span>

|<span data-ttu-id="7498c-114">ColumName</span><span class="sxs-lookup"><span data-stu-id="7498c-114">ColumnName</span></span>|<span data-ttu-id="7498c-115">DataType</span><span class="sxs-lookup"><span data-stu-id="7498c-115">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="7498c-116">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="7498c-116">TABLE_CAT</span></span>|<span data-ttu-id="7498c-117">String</span><span class="sxs-lookup"><span data-stu-id="7498c-117">String</span></span>|
|<span data-ttu-id="7498c-118">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="7498c-118">TABLE_SCHEM</span></span>|<span data-ttu-id="7498c-119">String</span><span class="sxs-lookup"><span data-stu-id="7498c-119">String</span></span>|
|<span data-ttu-id="7498c-120">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7498c-120">TABLE_NAME</span></span>|<span data-ttu-id="7498c-121">String</span><span class="sxs-lookup"><span data-stu-id="7498c-121">String</span></span>|
|<span data-ttu-id="7498c-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="7498c-122">TABLE_TYPE</span></span>|<span data-ttu-id="7498c-123">String</span><span class="sxs-lookup"><span data-stu-id="7498c-123">String</span></span>|
|<span data-ttu-id="7498c-124">REMARKS</span><span class="sxs-lookup"><span data-stu-id="7498c-124">REMARKS</span></span>|<span data-ttu-id="7498c-125">String</span><span class="sxs-lookup"><span data-stu-id="7498c-125">String</span></span>|

### <a name="indexes"></a><span data-ttu-id="7498c-126">Índices</span><span class="sxs-lookup"><span data-stu-id="7498c-126">Indexes</span></span>

|<span data-ttu-id="7498c-127">ColumName</span><span class="sxs-lookup"><span data-stu-id="7498c-127">ColumnName</span></span>|<span data-ttu-id="7498c-128">DataType</span><span class="sxs-lookup"><span data-stu-id="7498c-128">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="7498c-129">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="7498c-129">TABLE_CAT</span></span>|<span data-ttu-id="7498c-130">String</span><span class="sxs-lookup"><span data-stu-id="7498c-130">String</span></span>|
|<span data-ttu-id="7498c-131">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="7498c-131">TABLE_SCHEM</span></span>|<span data-ttu-id="7498c-132">String</span><span class="sxs-lookup"><span data-stu-id="7498c-132">String</span></span>|
|<span data-ttu-id="7498c-133">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7498c-133">TABLE_NAME</span></span>|<span data-ttu-id="7498c-134">String</span><span class="sxs-lookup"><span data-stu-id="7498c-134">String</span></span>|
|<span data-ttu-id="7498c-135">NON_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="7498c-135">NON_UNIQUE</span></span>|<span data-ttu-id="7498c-136">Int16</span><span class="sxs-lookup"><span data-stu-id="7498c-136">Int16</span></span>|
|<span data-ttu-id="7498c-137">INDEX_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="7498c-137">INDEX_QUALIFIER</span></span>|<span data-ttu-id="7498c-138">String</span><span class="sxs-lookup"><span data-stu-id="7498c-138">String</span></span>|
|<span data-ttu-id="7498c-139">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="7498c-139">INDEX_NAME</span></span>|<span data-ttu-id="7498c-140">String</span><span class="sxs-lookup"><span data-stu-id="7498c-140">String</span></span>|
|<span data-ttu-id="7498c-141">TYPE</span><span class="sxs-lookup"><span data-stu-id="7498c-141">TYPE</span></span>|<span data-ttu-id="7498c-142">Int16</span><span class="sxs-lookup"><span data-stu-id="7498c-142">Int16</span></span>|
|<span data-ttu-id="7498c-143">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="7498c-143">ORDINAL_POSITION</span></span>|<span data-ttu-id="7498c-144">Int16</span><span class="sxs-lookup"><span data-stu-id="7498c-144">Int16</span></span>|
|<span data-ttu-id="7498c-145">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="7498c-145">COLUMN_NAME</span></span>|<span data-ttu-id="7498c-146">String</span><span class="sxs-lookup"><span data-stu-id="7498c-146">String</span></span>|
|<span data-ttu-id="7498c-147">ASC_OR_DESC</span><span class="sxs-lookup"><span data-stu-id="7498c-147">ASC_OR_DESC</span></span>|<span data-ttu-id="7498c-148">String</span><span class="sxs-lookup"><span data-stu-id="7498c-148">String</span></span>|
|<span data-ttu-id="7498c-149">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="7498c-149">CARDINALITY</span></span>|<span data-ttu-id="7498c-150">Int32</span><span class="sxs-lookup"><span data-stu-id="7498c-150">Int32</span></span>|
|<span data-ttu-id="7498c-151">PAGES</span><span class="sxs-lookup"><span data-stu-id="7498c-151">PAGES</span></span>|<span data-ttu-id="7498c-152">Int32</span><span class="sxs-lookup"><span data-stu-id="7498c-152">Int32</span></span>|
|<span data-ttu-id="7498c-153">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="7498c-153">FILTER_CONDITION</span></span>|<span data-ttu-id="7498c-154">String</span><span class="sxs-lookup"><span data-stu-id="7498c-154">String</span></span>|
|<span data-ttu-id="7498c-155">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7498c-155">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="7498c-156">String</span><span class="sxs-lookup"><span data-stu-id="7498c-156">String</span></span>|
|<span data-ttu-id="7498c-157">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7498c-157">SS_DATA_TYPE</span></span>|<span data-ttu-id="7498c-158">Byte</span><span class="sxs-lookup"><span data-stu-id="7498c-158">Byte</span></span>|

### <a name="columns"></a><span data-ttu-id="7498c-159">Columnas</span><span class="sxs-lookup"><span data-stu-id="7498c-159">Columns</span></span>

|<span data-ttu-id="7498c-160">ColumName</span><span class="sxs-lookup"><span data-stu-id="7498c-160">ColumnName</span></span>|<span data-ttu-id="7498c-161">DataType</span><span class="sxs-lookup"><span data-stu-id="7498c-161">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="7498c-162">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="7498c-162">TABLE_CAT</span></span>|<span data-ttu-id="7498c-163">String</span><span class="sxs-lookup"><span data-stu-id="7498c-163">String</span></span>|
|<span data-ttu-id="7498c-164">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="7498c-164">TABLE_SCHEM</span></span>|<span data-ttu-id="7498c-165">String</span><span class="sxs-lookup"><span data-stu-id="7498c-165">String</span></span>|
|<span data-ttu-id="7498c-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7498c-166">TABLE_NAME</span></span>|<span data-ttu-id="7498c-167">String</span><span class="sxs-lookup"><span data-stu-id="7498c-167">String</span></span>|
|<span data-ttu-id="7498c-168">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="7498c-168">COLUMN_NAME</span></span>|<span data-ttu-id="7498c-169">String</span><span class="sxs-lookup"><span data-stu-id="7498c-169">String</span></span>|
|<span data-ttu-id="7498c-170">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7498c-170">DATA_TYPE</span></span>|<span data-ttu-id="7498c-171">Int16</span><span class="sxs-lookup"><span data-stu-id="7498c-171">Int16</span></span>|
|<span data-ttu-id="7498c-172">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="7498c-172">TYPE_NAME</span></span>|<span data-ttu-id="7498c-173">String</span><span class="sxs-lookup"><span data-stu-id="7498c-173">String</span></span>|
|<span data-ttu-id="7498c-174">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="7498c-174">COLUMN_SIZE</span></span>|<span data-ttu-id="7498c-175">Int32</span><span class="sxs-lookup"><span data-stu-id="7498c-175">Int32</span></span>|
|<span data-ttu-id="7498c-176">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="7498c-176">BUFFER_LENGTH</span></span>|<span data-ttu-id="7498c-177">Int32</span><span class="sxs-lookup"><span data-stu-id="7498c-177">Int32</span></span>|
|<span data-ttu-id="7498c-178">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="7498c-178">DECIMAL_DIGITS</span></span>|<span data-ttu-id="7498c-179">Int16</span><span class="sxs-lookup"><span data-stu-id="7498c-179">Int16</span></span>|
|<span data-ttu-id="7498c-180">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="7498c-180">NUM_PREC_RADIX</span></span>|<span data-ttu-id="7498c-181">Int16</span><span class="sxs-lookup"><span data-stu-id="7498c-181">Int16</span></span>|
|<span data-ttu-id="7498c-182">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="7498c-182">NULLABLE</span></span>|<span data-ttu-id="7498c-183">Int16</span><span class="sxs-lookup"><span data-stu-id="7498c-183">Int16</span></span>|
|<span data-ttu-id="7498c-184">REMARKS</span><span class="sxs-lookup"><span data-stu-id="7498c-184">REMARKS</span></span>|<span data-ttu-id="7498c-185">String</span><span class="sxs-lookup"><span data-stu-id="7498c-185">String</span></span>|
|<span data-ttu-id="7498c-186">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="7498c-186">COLUMN_DEF</span></span>|<span data-ttu-id="7498c-187">String</span><span class="sxs-lookup"><span data-stu-id="7498c-187">String</span></span>|
|<span data-ttu-id="7498c-188">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7498c-188">SQL_DATA_TYPE</span></span>|<span data-ttu-id="7498c-189">Int16</span><span class="sxs-lookup"><span data-stu-id="7498c-189">Int16</span></span>|
|<span data-ttu-id="7498c-190">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="7498c-190">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="7498c-191">Int16</span><span class="sxs-lookup"><span data-stu-id="7498c-191">Int16</span></span>|
|<span data-ttu-id="7498c-192">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="7498c-192">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="7498c-193">Int32</span><span class="sxs-lookup"><span data-stu-id="7498c-193">Int32</span></span>|
|<span data-ttu-id="7498c-194">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="7498c-194">ORDINAL_POSITION</span></span>|<span data-ttu-id="7498c-195">Int32</span><span class="sxs-lookup"><span data-stu-id="7498c-195">Int32</span></span>|
|<span data-ttu-id="7498c-196">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="7498c-196">IS_NULLABLE</span></span>|<span data-ttu-id="7498c-197">String</span><span class="sxs-lookup"><span data-stu-id="7498c-197">String</span></span>|
|<span data-ttu-id="7498c-198">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7498c-198">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="7498c-199">String</span><span class="sxs-lookup"><span data-stu-id="7498c-199">String</span></span>|
|<span data-ttu-id="7498c-200">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7498c-200">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="7498c-201">String</span><span class="sxs-lookup"><span data-stu-id="7498c-201">String</span></span>|
|<span data-ttu-id="7498c-202">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7498c-202">SS_DATA_TYPE</span></span>|<span data-ttu-id="7498c-203">Byte</span><span class="sxs-lookup"><span data-stu-id="7498c-203">Byte</span></span>|

### <a name="procedures"></a><span data-ttu-id="7498c-204">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="7498c-204">Procedures</span></span>

|<span data-ttu-id="7498c-205">ColumName</span><span class="sxs-lookup"><span data-stu-id="7498c-205">ColumnName</span></span>|<span data-ttu-id="7498c-206">DataType</span><span class="sxs-lookup"><span data-stu-id="7498c-206">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="7498c-207">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="7498c-207">PROCEDURE_CAT</span></span>|<span data-ttu-id="7498c-208">String</span><span class="sxs-lookup"><span data-stu-id="7498c-208">String</span></span>|
|<span data-ttu-id="7498c-209">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="7498c-209">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="7498c-210">String</span><span class="sxs-lookup"><span data-stu-id="7498c-210">String</span></span>|
|<span data-ttu-id="7498c-211">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="7498c-211">PROCEDURE_NAME</span></span>|<span data-ttu-id="7498c-212">String</span><span class="sxs-lookup"><span data-stu-id="7498c-212">String</span></span>|
|<span data-ttu-id="7498c-213">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="7498c-213">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="7498c-214">Int32</span><span class="sxs-lookup"><span data-stu-id="7498c-214">Int32</span></span>|
|<span data-ttu-id="7498c-215">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="7498c-215">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="7498c-216">Int32</span><span class="sxs-lookup"><span data-stu-id="7498c-216">Int32</span></span>|
|<span data-ttu-id="7498c-217">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="7498c-217">NUM_RESULT_SETS</span></span>|<span data-ttu-id="7498c-218">Int32</span><span class="sxs-lookup"><span data-stu-id="7498c-218">Int32</span></span>|
|<span data-ttu-id="7498c-219">REMARKS</span><span class="sxs-lookup"><span data-stu-id="7498c-219">REMARKS</span></span>|<span data-ttu-id="7498c-220">String</span><span class="sxs-lookup"><span data-stu-id="7498c-220">String</span></span>|
|<span data-ttu-id="7498c-221">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="7498c-221">PROCEDURE_TYPE</span></span>|<span data-ttu-id="7498c-222">Int16</span><span class="sxs-lookup"><span data-stu-id="7498c-222">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="7498c-223">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="7498c-223">ProcedureColumns</span></span>

|<span data-ttu-id="7498c-224">ColumName</span><span class="sxs-lookup"><span data-stu-id="7498c-224">ColumnName</span></span>|<span data-ttu-id="7498c-225">DataType</span><span class="sxs-lookup"><span data-stu-id="7498c-225">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="7498c-226">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="7498c-226">PROCEDURE_CAT</span></span>|<span data-ttu-id="7498c-227">String</span><span class="sxs-lookup"><span data-stu-id="7498c-227">String</span></span>|
|<span data-ttu-id="7498c-228">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="7498c-228">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="7498c-229">String</span><span class="sxs-lookup"><span data-stu-id="7498c-229">String</span></span>|
|<span data-ttu-id="7498c-230">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="7498c-230">PROCEDURE_NAME</span></span>|<span data-ttu-id="7498c-231">String</span><span class="sxs-lookup"><span data-stu-id="7498c-231">String</span></span>|
|<span data-ttu-id="7498c-232">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="7498c-232">COLUMN_NAME</span></span>|<span data-ttu-id="7498c-233">String</span><span class="sxs-lookup"><span data-stu-id="7498c-233">String</span></span>|
|<span data-ttu-id="7498c-234">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="7498c-234">COLUMN_TYPE</span></span>|<span data-ttu-id="7498c-235">Int16</span><span class="sxs-lookup"><span data-stu-id="7498c-235">Int16</span></span>|
|<span data-ttu-id="7498c-236">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7498c-236">DATA_TYPE</span></span>|<span data-ttu-id="7498c-237">Int16</span><span class="sxs-lookup"><span data-stu-id="7498c-237">Int16</span></span>|
|<span data-ttu-id="7498c-238">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="7498c-238">TYPE_NAME</span></span>|<span data-ttu-id="7498c-239">String</span><span class="sxs-lookup"><span data-stu-id="7498c-239">String</span></span>|
|<span data-ttu-id="7498c-240">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="7498c-240">COLUMN_SIZE</span></span>|<span data-ttu-id="7498c-241">Int32</span><span class="sxs-lookup"><span data-stu-id="7498c-241">Int32</span></span>|
|<span data-ttu-id="7498c-242">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="7498c-242">BUFFER_LENGTH</span></span>|<span data-ttu-id="7498c-243">Int32</span><span class="sxs-lookup"><span data-stu-id="7498c-243">Int32</span></span>|
|<span data-ttu-id="7498c-244">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="7498c-244">DECIMAL_DIGITS</span></span>|<span data-ttu-id="7498c-245">Int16</span><span class="sxs-lookup"><span data-stu-id="7498c-245">Int16</span></span>|
|<span data-ttu-id="7498c-246">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="7498c-246">NUM_PREC_RADIX</span></span>|<span data-ttu-id="7498c-247">Int16</span><span class="sxs-lookup"><span data-stu-id="7498c-247">Int16</span></span>|
|<span data-ttu-id="7498c-248">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="7498c-248">NULLABLE</span></span>|<span data-ttu-id="7498c-249">Int16</span><span class="sxs-lookup"><span data-stu-id="7498c-249">Int16</span></span>|
|<span data-ttu-id="7498c-250">REMARKS</span><span class="sxs-lookup"><span data-stu-id="7498c-250">REMARKS</span></span>|<span data-ttu-id="7498c-251">String</span><span class="sxs-lookup"><span data-stu-id="7498c-251">String</span></span>|
|<span data-ttu-id="7498c-252">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="7498c-252">COLUMN_DEF</span></span>|<span data-ttu-id="7498c-253">String</span><span class="sxs-lookup"><span data-stu-id="7498c-253">String</span></span>|
|<span data-ttu-id="7498c-254">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7498c-254">SQL_DATA_TYPE</span></span>|<span data-ttu-id="7498c-255">Int16</span><span class="sxs-lookup"><span data-stu-id="7498c-255">Int16</span></span>|
|<span data-ttu-id="7498c-256">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="7498c-256">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="7498c-257">Int16</span><span class="sxs-lookup"><span data-stu-id="7498c-257">Int16</span></span>|
|<span data-ttu-id="7498c-258">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="7498c-258">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="7498c-259">Int32</span><span class="sxs-lookup"><span data-stu-id="7498c-259">Int32</span></span>|
|<span data-ttu-id="7498c-260">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="7498c-260">ORDINAL_POSITION</span></span>|<span data-ttu-id="7498c-261">Int32</span><span class="sxs-lookup"><span data-stu-id="7498c-261">Int32</span></span>|
|<span data-ttu-id="7498c-262">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="7498c-262">IS_NULLABLE</span></span>|<span data-ttu-id="7498c-263">String</span><span class="sxs-lookup"><span data-stu-id="7498c-263">String</span></span>|
|<span data-ttu-id="7498c-264">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7498c-264">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="7498c-265">String</span><span class="sxs-lookup"><span data-stu-id="7498c-265">String</span></span>|
|<span data-ttu-id="7498c-266">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7498c-266">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="7498c-267">String</span><span class="sxs-lookup"><span data-stu-id="7498c-267">String</span></span>|
|<span data-ttu-id="7498c-268">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7498c-268">SS_DATA_TYPE</span></span>|<span data-ttu-id="7498c-269">Byte</span><span class="sxs-lookup"><span data-stu-id="7498c-269">Byte</span></span>|

### <a name="procedureparameters"></a><span data-ttu-id="7498c-270">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="7498c-270">ProcedureParameters</span></span>

|<span data-ttu-id="7498c-271">ColumName</span><span class="sxs-lookup"><span data-stu-id="7498c-271">ColumnName</span></span>|<span data-ttu-id="7498c-272">DataType</span><span class="sxs-lookup"><span data-stu-id="7498c-272">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="7498c-273">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="7498c-273">PROCEDURE_CAT</span></span>|<span data-ttu-id="7498c-274">String</span><span class="sxs-lookup"><span data-stu-id="7498c-274">String</span></span>|
|<span data-ttu-id="7498c-275">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="7498c-275">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="7498c-276">String</span><span class="sxs-lookup"><span data-stu-id="7498c-276">String</span></span>|
|<span data-ttu-id="7498c-277">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="7498c-277">PROCEDURE_NAME</span></span>|<span data-ttu-id="7498c-278">String</span><span class="sxs-lookup"><span data-stu-id="7498c-278">String</span></span>|
|<span data-ttu-id="7498c-279">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="7498c-279">COLUMN_NAME</span></span>|<span data-ttu-id="7498c-280">String</span><span class="sxs-lookup"><span data-stu-id="7498c-280">String</span></span>|
|<span data-ttu-id="7498c-281">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="7498c-281">COLUMN_TYPE</span></span>|<span data-ttu-id="7498c-282">Int16</span><span class="sxs-lookup"><span data-stu-id="7498c-282">Int16</span></span>|
|<span data-ttu-id="7498c-283">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7498c-283">DATA_TYPE</span></span>|<span data-ttu-id="7498c-284">Int16</span><span class="sxs-lookup"><span data-stu-id="7498c-284">Int16</span></span>|
|<span data-ttu-id="7498c-285">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="7498c-285">TYPE_NAME</span></span>|<span data-ttu-id="7498c-286">String</span><span class="sxs-lookup"><span data-stu-id="7498c-286">String</span></span>|
|<span data-ttu-id="7498c-287">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="7498c-287">COLUMN_SIZE</span></span>|<span data-ttu-id="7498c-288">Int32</span><span class="sxs-lookup"><span data-stu-id="7498c-288">Int32</span></span>|
|<span data-ttu-id="7498c-289">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="7498c-289">BUFFER_LENGTH</span></span>|<span data-ttu-id="7498c-290">Int32</span><span class="sxs-lookup"><span data-stu-id="7498c-290">Int32</span></span>|
|<span data-ttu-id="7498c-291">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="7498c-291">DECIMAL_DIGITS</span></span>|<span data-ttu-id="7498c-292">Int16</span><span class="sxs-lookup"><span data-stu-id="7498c-292">Int16</span></span>|
|<span data-ttu-id="7498c-293">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="7498c-293">NUM_PREC_RADIX</span></span>|<span data-ttu-id="7498c-294">Int16</span><span class="sxs-lookup"><span data-stu-id="7498c-294">Int16</span></span>|
|<span data-ttu-id="7498c-295">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="7498c-295">NULLABLE</span></span>|<span data-ttu-id="7498c-296">Int16</span><span class="sxs-lookup"><span data-stu-id="7498c-296">Int16</span></span>|
|<span data-ttu-id="7498c-297">REMARKS</span><span class="sxs-lookup"><span data-stu-id="7498c-297">REMARKS</span></span>|<span data-ttu-id="7498c-298">String</span><span class="sxs-lookup"><span data-stu-id="7498c-298">String</span></span>|
|<span data-ttu-id="7498c-299">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="7498c-299">COLUMN_DEF</span></span>|<span data-ttu-id="7498c-300">String</span><span class="sxs-lookup"><span data-stu-id="7498c-300">String</span></span>|
|<span data-ttu-id="7498c-301">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7498c-301">SQL_DATA_TYPE</span></span>|<span data-ttu-id="7498c-302">Int16</span><span class="sxs-lookup"><span data-stu-id="7498c-302">Int16</span></span>|
|<span data-ttu-id="7498c-303">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="7498c-303">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="7498c-304">Int16</span><span class="sxs-lookup"><span data-stu-id="7498c-304">Int16</span></span>|
|<span data-ttu-id="7498c-305">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="7498c-305">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="7498c-306">Int32</span><span class="sxs-lookup"><span data-stu-id="7498c-306">Int32</span></span>|
|<span data-ttu-id="7498c-307">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="7498c-307">ORDINAL_POSITION</span></span>|<span data-ttu-id="7498c-308">Int32</span><span class="sxs-lookup"><span data-stu-id="7498c-308">Int32</span></span>|
|<span data-ttu-id="7498c-309">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="7498c-309">IS_NULLABLE</span></span>|<span data-ttu-id="7498c-310">String</span><span class="sxs-lookup"><span data-stu-id="7498c-310">String</span></span>|
|<span data-ttu-id="7498c-311">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7498c-311">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="7498c-312">String</span><span class="sxs-lookup"><span data-stu-id="7498c-312">String</span></span>|
|<span data-ttu-id="7498c-313">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7498c-313">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="7498c-314">String</span><span class="sxs-lookup"><span data-stu-id="7498c-314">String</span></span>|
|<span data-ttu-id="7498c-315">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7498c-315">SS_DATA_TYPE</span></span>|<span data-ttu-id="7498c-316">Byte</span><span class="sxs-lookup"><span data-stu-id="7498c-316">Byte</span></span>|

## <a name="microsoft-oracle-odbc-driver"></a><span data-ttu-id="7498c-317">Controlador ODBC para Oracle de Microsoft</span><span class="sxs-lookup"><span data-stu-id="7498c-317">Microsoft Oracle ODBC Driver</span></span>

<span data-ttu-id="7498c-318">El controlador ODBC de Oracle de Microsoft SQL Server admite las siguientes colecciones de esquemas específicas además de las colecciones de esquemas comunes:</span><span class="sxs-lookup"><span data-stu-id="7498c-318">The Microsoft SQL Server Oracle ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="7498c-319">Tablas</span><span class="sxs-lookup"><span data-stu-id="7498c-319">Tables</span></span>

- <span data-ttu-id="7498c-320">Columnas</span><span class="sxs-lookup"><span data-stu-id="7498c-320">Columns</span></span>

- <span data-ttu-id="7498c-321">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="7498c-321">Procedures</span></span>

- <span data-ttu-id="7498c-322">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="7498c-322">ProcedureColumns</span></span>

- <span data-ttu-id="7498c-323">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="7498c-323">ProcedureParameters</span></span>

- <span data-ttu-id="7498c-324">Vistas</span><span class="sxs-lookup"><span data-stu-id="7498c-324">Views</span></span>

- <span data-ttu-id="7498c-325">Índices</span><span class="sxs-lookup"><span data-stu-id="7498c-325">Indexes</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="7498c-326">Tablas y vistas</span><span class="sxs-lookup"><span data-stu-id="7498c-326">Tables and Views</span></span>

|<span data-ttu-id="7498c-327">ColumName</span><span class="sxs-lookup"><span data-stu-id="7498c-327">ColumnName</span></span>|<span data-ttu-id="7498c-328">DataType</span><span class="sxs-lookup"><span data-stu-id="7498c-328">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="7498c-329">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="7498c-329">TABLE_QUALIFIER</span></span>|<span data-ttu-id="7498c-330">String</span><span class="sxs-lookup"><span data-stu-id="7498c-330">String</span></span>|
|<span data-ttu-id="7498c-331">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="7498c-331">TABLE_OWNER</span></span>|<span data-ttu-id="7498c-332">String</span><span class="sxs-lookup"><span data-stu-id="7498c-332">String</span></span>|
|<span data-ttu-id="7498c-333">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7498c-333">TABLE_NAME</span></span>|<span data-ttu-id="7498c-334">String</span><span class="sxs-lookup"><span data-stu-id="7498c-334">String</span></span>|
|<span data-ttu-id="7498c-335">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="7498c-335">TABLE_TYPE</span></span>|<span data-ttu-id="7498c-336">String</span><span class="sxs-lookup"><span data-stu-id="7498c-336">String</span></span>|
|<span data-ttu-id="7498c-337">REMARKS</span><span class="sxs-lookup"><span data-stu-id="7498c-337">REMARKS</span></span>|<span data-ttu-id="7498c-338">String</span><span class="sxs-lookup"><span data-stu-id="7498c-338">String</span></span>|

### <a name="columns"></a><span data-ttu-id="7498c-339">Columnas</span><span class="sxs-lookup"><span data-stu-id="7498c-339">Columns</span></span>

|<span data-ttu-id="7498c-340">ColumName</span><span class="sxs-lookup"><span data-stu-id="7498c-340">ColumnName</span></span>|<span data-ttu-id="7498c-341">DataType</span><span class="sxs-lookup"><span data-stu-id="7498c-341">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="7498c-342">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="7498c-342">TABLE_QUALIFIER</span></span>|<span data-ttu-id="7498c-343">String</span><span class="sxs-lookup"><span data-stu-id="7498c-343">String</span></span>|
|<span data-ttu-id="7498c-344">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="7498c-344">TABLE_OWNER</span></span>|<span data-ttu-id="7498c-345">String</span><span class="sxs-lookup"><span data-stu-id="7498c-345">String</span></span>|
|<span data-ttu-id="7498c-346">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7498c-346">TABLE_NAME</span></span>|<span data-ttu-id="7498c-347">String</span><span class="sxs-lookup"><span data-stu-id="7498c-347">String</span></span>|
|<span data-ttu-id="7498c-348">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="7498c-348">COLUMN_NAME</span></span>|<span data-ttu-id="7498c-349">String</span><span class="sxs-lookup"><span data-stu-id="7498c-349">String</span></span>|
|<span data-ttu-id="7498c-350">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7498c-350">DATA_TYPE</span></span>|<span data-ttu-id="7498c-351">Int16</span><span class="sxs-lookup"><span data-stu-id="7498c-351">Int16</span></span>|
|<span data-ttu-id="7498c-352">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="7498c-352">TYPE_NAME</span></span>|<span data-ttu-id="7498c-353">String</span><span class="sxs-lookup"><span data-stu-id="7498c-353">String</span></span>|
|<span data-ttu-id="7498c-354">PRECISION</span><span class="sxs-lookup"><span data-stu-id="7498c-354">PRECISION</span></span>|<span data-ttu-id="7498c-355">Int32</span><span class="sxs-lookup"><span data-stu-id="7498c-355">Int32</span></span>|
|<span data-ttu-id="7498c-356">LENGTH</span><span class="sxs-lookup"><span data-stu-id="7498c-356">LENGTH</span></span>|<span data-ttu-id="7498c-357">Int32</span><span class="sxs-lookup"><span data-stu-id="7498c-357">Int32</span></span>|
|<span data-ttu-id="7498c-358">SCALE</span><span class="sxs-lookup"><span data-stu-id="7498c-358">SCALE</span></span>|<span data-ttu-id="7498c-359">Int16</span><span class="sxs-lookup"><span data-stu-id="7498c-359">Int16</span></span>|
|<span data-ttu-id="7498c-360">RADIX</span><span class="sxs-lookup"><span data-stu-id="7498c-360">RADIX</span></span>|<span data-ttu-id="7498c-361">Int16</span><span class="sxs-lookup"><span data-stu-id="7498c-361">Int16</span></span>|
|<span data-ttu-id="7498c-362">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="7498c-362">NULLABLE</span></span>|<span data-ttu-id="7498c-363">Int16</span><span class="sxs-lookup"><span data-stu-id="7498c-363">Int16</span></span>|
|<span data-ttu-id="7498c-364">REMARKS</span><span class="sxs-lookup"><span data-stu-id="7498c-364">REMARKS</span></span>|<span data-ttu-id="7498c-365">String</span><span class="sxs-lookup"><span data-stu-id="7498c-365">String</span></span>|
|<span data-ttu-id="7498c-366">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="7498c-366">ORDINAL_POSITION</span></span>|<span data-ttu-id="7498c-367">Int32</span><span class="sxs-lookup"><span data-stu-id="7498c-367">Int32</span></span>|

### <a name="procedures"></a><span data-ttu-id="7498c-368">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="7498c-368">Procedures</span></span>

|<span data-ttu-id="7498c-369">ColumName</span><span class="sxs-lookup"><span data-stu-id="7498c-369">ColumnName</span></span>|<span data-ttu-id="7498c-370">DataType</span><span class="sxs-lookup"><span data-stu-id="7498c-370">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="7498c-371">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="7498c-371">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="7498c-372">String</span><span class="sxs-lookup"><span data-stu-id="7498c-372">String</span></span>|
|<span data-ttu-id="7498c-373">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="7498c-373">PROCEDURE_OWNER</span></span>|<span data-ttu-id="7498c-374">String</span><span class="sxs-lookup"><span data-stu-id="7498c-374">String</span></span>|
|<span data-ttu-id="7498c-375">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="7498c-375">PROCEDURE_NAME</span></span>|<span data-ttu-id="7498c-376">String</span><span class="sxs-lookup"><span data-stu-id="7498c-376">String</span></span>|
|<span data-ttu-id="7498c-377">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="7498c-377">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="7498c-378">Int16</span><span class="sxs-lookup"><span data-stu-id="7498c-378">Int16</span></span>|
|<span data-ttu-id="7498c-379">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="7498c-379">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="7498c-380">Int16</span><span class="sxs-lookup"><span data-stu-id="7498c-380">Int16</span></span>|
|<span data-ttu-id="7498c-381">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="7498c-381">NUM_RESULT_SETS</span></span>|<span data-ttu-id="7498c-382">Int16</span><span class="sxs-lookup"><span data-stu-id="7498c-382">Int16</span></span>|
|<span data-ttu-id="7498c-383">REMARKS</span><span class="sxs-lookup"><span data-stu-id="7498c-383">REMARKS</span></span>|<span data-ttu-id="7498c-384">String</span><span class="sxs-lookup"><span data-stu-id="7498c-384">String</span></span>|
|<span data-ttu-id="7498c-385">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="7498c-385">PROCEDURE_TYPE</span></span>|<span data-ttu-id="7498c-386">Int16</span><span class="sxs-lookup"><span data-stu-id="7498c-386">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="7498c-387">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="7498c-387">ProcedureColumns</span></span>

|<span data-ttu-id="7498c-388">ColumName</span><span class="sxs-lookup"><span data-stu-id="7498c-388">ColumnName</span></span>|<span data-ttu-id="7498c-389">DataType</span><span class="sxs-lookup"><span data-stu-id="7498c-389">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="7498c-390">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="7498c-390">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="7498c-391">String</span><span class="sxs-lookup"><span data-stu-id="7498c-391">String</span></span>|
|<span data-ttu-id="7498c-392">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="7498c-392">PROCEDURE_OWNER</span></span>|<span data-ttu-id="7498c-393">String</span><span class="sxs-lookup"><span data-stu-id="7498c-393">String</span></span>|
|<span data-ttu-id="7498c-394">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="7498c-394">PROCEDURE_NAME</span></span>|<span data-ttu-id="7498c-395">String</span><span class="sxs-lookup"><span data-stu-id="7498c-395">String</span></span>|
|<span data-ttu-id="7498c-396">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="7498c-396">COLUMN_NAME</span></span>|<span data-ttu-id="7498c-397">String</span><span class="sxs-lookup"><span data-stu-id="7498c-397">String</span></span>|
|<span data-ttu-id="7498c-398">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="7498c-398">COLUMN_TYPE</span></span>|<span data-ttu-id="7498c-399">Int16</span><span class="sxs-lookup"><span data-stu-id="7498c-399">Int16</span></span>|
|<span data-ttu-id="7498c-400">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7498c-400">DATA_TYPE</span></span>|<span data-ttu-id="7498c-401">Int16</span><span class="sxs-lookup"><span data-stu-id="7498c-401">Int16</span></span>|
|<span data-ttu-id="7498c-402">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="7498c-402">TYPE_NAME</span></span>|<span data-ttu-id="7498c-403">String</span><span class="sxs-lookup"><span data-stu-id="7498c-403">String</span></span>|
|<span data-ttu-id="7498c-404">PRECISION</span><span class="sxs-lookup"><span data-stu-id="7498c-404">PRECISION</span></span>|<span data-ttu-id="7498c-405">Int32</span><span class="sxs-lookup"><span data-stu-id="7498c-405">Int32</span></span>|
|<span data-ttu-id="7498c-406">LENGTH</span><span class="sxs-lookup"><span data-stu-id="7498c-406">LENGTH</span></span>|<span data-ttu-id="7498c-407">Int32</span><span class="sxs-lookup"><span data-stu-id="7498c-407">Int32</span></span>|
|<span data-ttu-id="7498c-408">SCALE</span><span class="sxs-lookup"><span data-stu-id="7498c-408">SCALE</span></span>|<span data-ttu-id="7498c-409">Int16</span><span class="sxs-lookup"><span data-stu-id="7498c-409">Int16</span></span>|
|<span data-ttu-id="7498c-410">RADIX</span><span class="sxs-lookup"><span data-stu-id="7498c-410">RADIX</span></span>|<span data-ttu-id="7498c-411">Int16</span><span class="sxs-lookup"><span data-stu-id="7498c-411">Int16</span></span>|
|<span data-ttu-id="7498c-412">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="7498c-412">NULLABLE</span></span>|<span data-ttu-id="7498c-413">Int16</span><span class="sxs-lookup"><span data-stu-id="7498c-413">Int16</span></span>|
|<span data-ttu-id="7498c-414">REMARKS</span><span class="sxs-lookup"><span data-stu-id="7498c-414">REMARKS</span></span>|<span data-ttu-id="7498c-415">String</span><span class="sxs-lookup"><span data-stu-id="7498c-415">String</span></span>|
|<span data-ttu-id="7498c-416">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="7498c-416">OVERLOAD</span></span>|<span data-ttu-id="7498c-417">Int32</span><span class="sxs-lookup"><span data-stu-id="7498c-417">Int32</span></span>|
|<span data-ttu-id="7498c-418">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="7498c-418">ORDINAL_POSITION</span></span>|<span data-ttu-id="7498c-419">Int32</span><span class="sxs-lookup"><span data-stu-id="7498c-419">Int32</span></span>|

## <a name="microsoft-jet-odbc-driver"></a><span data-ttu-id="7498c-420">Controlador ODBC de Microsoft para Jet</span><span class="sxs-lookup"><span data-stu-id="7498c-420">Microsoft Jet ODBC Driver</span></span>

<span data-ttu-id="7498c-421">El controlador ODBC de Microsoft para Jet admite, además de las colecciones de esquemas comunes, las siguientes colecciones de esquemas específicas:</span><span class="sxs-lookup"><span data-stu-id="7498c-421">The Microsoft Jet ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="7498c-422">Tablas</span><span class="sxs-lookup"><span data-stu-id="7498c-422">Tables</span></span>

- <span data-ttu-id="7498c-423">Índices</span><span class="sxs-lookup"><span data-stu-id="7498c-423">Indexes</span></span>

- <span data-ttu-id="7498c-424">Columnas</span><span class="sxs-lookup"><span data-stu-id="7498c-424">Columns</span></span>

- <span data-ttu-id="7498c-425">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="7498c-425">Procedures</span></span>

- <span data-ttu-id="7498c-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="7498c-426">ProcedureColumns</span></span>

- <span data-ttu-id="7498c-427">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="7498c-427">ProcedureParameters</span></span>

- <span data-ttu-id="7498c-428">Vistas</span><span class="sxs-lookup"><span data-stu-id="7498c-428">Views</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="7498c-429">Tablas y vistas</span><span class="sxs-lookup"><span data-stu-id="7498c-429">Tables and Views</span></span>

|<span data-ttu-id="7498c-430">ColumName</span><span class="sxs-lookup"><span data-stu-id="7498c-430">ColumnName</span></span>|<span data-ttu-id="7498c-431">DataType</span><span class="sxs-lookup"><span data-stu-id="7498c-431">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="7498c-432">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="7498c-432">TABLE_QUALIFIER</span></span>|<span data-ttu-id="7498c-433">String</span><span class="sxs-lookup"><span data-stu-id="7498c-433">String</span></span>|
|<span data-ttu-id="7498c-434">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="7498c-434">TABLE_OWNER</span></span>|<span data-ttu-id="7498c-435">String</span><span class="sxs-lookup"><span data-stu-id="7498c-435">String</span></span>|
|<span data-ttu-id="7498c-436">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7498c-436">TABLE_NAME</span></span>|<span data-ttu-id="7498c-437">String</span><span class="sxs-lookup"><span data-stu-id="7498c-437">String</span></span>|
|<span data-ttu-id="7498c-438">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="7498c-438">TABLE_TYPE</span></span>|<span data-ttu-id="7498c-439">String</span><span class="sxs-lookup"><span data-stu-id="7498c-439">String</span></span>|
|<span data-ttu-id="7498c-440">REMARKS</span><span class="sxs-lookup"><span data-stu-id="7498c-440">REMARKS</span></span>|<span data-ttu-id="7498c-441">String</span><span class="sxs-lookup"><span data-stu-id="7498c-441">String</span></span>|

### <a name="columns"></a><span data-ttu-id="7498c-442">Columnas</span><span class="sxs-lookup"><span data-stu-id="7498c-442">Columns</span></span>

|<span data-ttu-id="7498c-443">ColumName</span><span class="sxs-lookup"><span data-stu-id="7498c-443">ColumnName</span></span>|<span data-ttu-id="7498c-444">DataType</span><span class="sxs-lookup"><span data-stu-id="7498c-444">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="7498c-445">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="7498c-445">TABLE_QUALIFIER</span></span>|<span data-ttu-id="7498c-446">String</span><span class="sxs-lookup"><span data-stu-id="7498c-446">String</span></span>|
|<span data-ttu-id="7498c-447">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="7498c-447">TABLE_OWNER</span></span>|<span data-ttu-id="7498c-448">String</span><span class="sxs-lookup"><span data-stu-id="7498c-448">String</span></span>|
|<span data-ttu-id="7498c-449">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7498c-449">TABLE_NAME</span></span>|<span data-ttu-id="7498c-450">String</span><span class="sxs-lookup"><span data-stu-id="7498c-450">String</span></span>|
|<span data-ttu-id="7498c-451">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="7498c-451">COLUMN_NAME</span></span>|<span data-ttu-id="7498c-452">String</span><span class="sxs-lookup"><span data-stu-id="7498c-452">String</span></span>|
|<span data-ttu-id="7498c-453">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7498c-453">DATA_TYPE</span></span>|<span data-ttu-id="7498c-454">Int16</span><span class="sxs-lookup"><span data-stu-id="7498c-454">Int16</span></span>|
|<span data-ttu-id="7498c-455">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="7498c-455">TYPE_NAME</span></span>|<span data-ttu-id="7498c-456">String</span><span class="sxs-lookup"><span data-stu-id="7498c-456">String</span></span>|
|<span data-ttu-id="7498c-457">PRECISION</span><span class="sxs-lookup"><span data-stu-id="7498c-457">PRECISION</span></span>|<span data-ttu-id="7498c-458">Int32</span><span class="sxs-lookup"><span data-stu-id="7498c-458">Int32</span></span>|
|<span data-ttu-id="7498c-459">LENGTH</span><span class="sxs-lookup"><span data-stu-id="7498c-459">LENGTH</span></span>|<span data-ttu-id="7498c-460">Int32</span><span class="sxs-lookup"><span data-stu-id="7498c-460">Int32</span></span>|
|<span data-ttu-id="7498c-461">SCALE</span><span class="sxs-lookup"><span data-stu-id="7498c-461">SCALE</span></span>|<span data-ttu-id="7498c-462">Int16</span><span class="sxs-lookup"><span data-stu-id="7498c-462">Int16</span></span>|
|<span data-ttu-id="7498c-463">RADIX</span><span class="sxs-lookup"><span data-stu-id="7498c-463">RADIX</span></span>|<span data-ttu-id="7498c-464">Int16</span><span class="sxs-lookup"><span data-stu-id="7498c-464">Int16</span></span>|
|<span data-ttu-id="7498c-465">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="7498c-465">NULLABLE</span></span>|<span data-ttu-id="7498c-466">Int16</span><span class="sxs-lookup"><span data-stu-id="7498c-466">Int16</span></span>|
|<span data-ttu-id="7498c-467">REMARKS</span><span class="sxs-lookup"><span data-stu-id="7498c-467">REMARKS</span></span>|<span data-ttu-id="7498c-468">String</span><span class="sxs-lookup"><span data-stu-id="7498c-468">String</span></span>|
|<span data-ttu-id="7498c-469">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="7498c-469">ORDINAL_POSITION</span></span>|<span data-ttu-id="7498c-470">Int32</span><span class="sxs-lookup"><span data-stu-id="7498c-470">Int32</span></span>|

### <a name="procedures"></a><span data-ttu-id="7498c-471">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="7498c-471">Procedures</span></span>

|<span data-ttu-id="7498c-472">ColumName</span><span class="sxs-lookup"><span data-stu-id="7498c-472">ColumnName</span></span>|<span data-ttu-id="7498c-473">DataType</span><span class="sxs-lookup"><span data-stu-id="7498c-473">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="7498c-474">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="7498c-474">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="7498c-475">String</span><span class="sxs-lookup"><span data-stu-id="7498c-475">String</span></span>|
|<span data-ttu-id="7498c-476">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="7498c-476">PROCEDURE_OWNER</span></span>|<span data-ttu-id="7498c-477">String</span><span class="sxs-lookup"><span data-stu-id="7498c-477">String</span></span>|
|<span data-ttu-id="7498c-478">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="7498c-478">PROCEDURE_NAME</span></span>|<span data-ttu-id="7498c-479">String</span><span class="sxs-lookup"><span data-stu-id="7498c-479">String</span></span>|
|<span data-ttu-id="7498c-480">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="7498c-480">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="7498c-481">Int16</span><span class="sxs-lookup"><span data-stu-id="7498c-481">Int16</span></span>|
|<span data-ttu-id="7498c-482">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="7498c-482">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="7498c-483">Int16</span><span class="sxs-lookup"><span data-stu-id="7498c-483">Int16</span></span>|
|<span data-ttu-id="7498c-484">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="7498c-484">NUM_RESULT_SETS</span></span>|<span data-ttu-id="7498c-485">Int16</span><span class="sxs-lookup"><span data-stu-id="7498c-485">Int16</span></span>|
|<span data-ttu-id="7498c-486">REMARKS</span><span class="sxs-lookup"><span data-stu-id="7498c-486">REMARKS</span></span>|<span data-ttu-id="7498c-487">String</span><span class="sxs-lookup"><span data-stu-id="7498c-487">String</span></span>|
|<span data-ttu-id="7498c-488">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="7498c-488">PROCEDURE_TYPE</span></span>|<span data-ttu-id="7498c-489">Int16</span><span class="sxs-lookup"><span data-stu-id="7498c-489">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="7498c-490">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="7498c-490">ProcedureColumns</span></span>

|<span data-ttu-id="7498c-491">ColumName</span><span class="sxs-lookup"><span data-stu-id="7498c-491">ColumnName</span></span>|<span data-ttu-id="7498c-492">DataType</span><span class="sxs-lookup"><span data-stu-id="7498c-492">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="7498c-493">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="7498c-493">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="7498c-494">String</span><span class="sxs-lookup"><span data-stu-id="7498c-494">String</span></span>|
|<span data-ttu-id="7498c-495">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="7498c-495">PROCEDURE_OWNER</span></span>|<span data-ttu-id="7498c-496">String</span><span class="sxs-lookup"><span data-stu-id="7498c-496">String</span></span>|
|<span data-ttu-id="7498c-497">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="7498c-497">PROCEDURE_NAME</span></span>|<span data-ttu-id="7498c-498">String</span><span class="sxs-lookup"><span data-stu-id="7498c-498">String</span></span>|
|<span data-ttu-id="7498c-499">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="7498c-499">COLUMN_NAME</span></span>|<span data-ttu-id="7498c-500">String</span><span class="sxs-lookup"><span data-stu-id="7498c-500">String</span></span>|
|<span data-ttu-id="7498c-501">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="7498c-501">COLUMN_TYPE</span></span>|<span data-ttu-id="7498c-502">Int16</span><span class="sxs-lookup"><span data-stu-id="7498c-502">Int16</span></span>|
|<span data-ttu-id="7498c-503">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7498c-503">DATA_TYPE</span></span>|<span data-ttu-id="7498c-504">Int16</span><span class="sxs-lookup"><span data-stu-id="7498c-504">Int16</span></span>|
|<span data-ttu-id="7498c-505">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="7498c-505">TYPE_NAME</span></span>|<span data-ttu-id="7498c-506">String</span><span class="sxs-lookup"><span data-stu-id="7498c-506">String</span></span>|
|<span data-ttu-id="7498c-507">PRECISION</span><span class="sxs-lookup"><span data-stu-id="7498c-507">PRECISION</span></span>|<span data-ttu-id="7498c-508">Int32</span><span class="sxs-lookup"><span data-stu-id="7498c-508">Int32</span></span>|
|<span data-ttu-id="7498c-509">LENGTH</span><span class="sxs-lookup"><span data-stu-id="7498c-509">LENGTH</span></span>|<span data-ttu-id="7498c-510">Int32</span><span class="sxs-lookup"><span data-stu-id="7498c-510">Int32</span></span>|
|<span data-ttu-id="7498c-511">SCALE</span><span class="sxs-lookup"><span data-stu-id="7498c-511">SCALE</span></span>|<span data-ttu-id="7498c-512">Int16</span><span class="sxs-lookup"><span data-stu-id="7498c-512">Int16</span></span>|
|<span data-ttu-id="7498c-513">RADIX</span><span class="sxs-lookup"><span data-stu-id="7498c-513">RADIX</span></span>|<span data-ttu-id="7498c-514">Int16</span><span class="sxs-lookup"><span data-stu-id="7498c-514">Int16</span></span>|
|<span data-ttu-id="7498c-515">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="7498c-515">NULLABLE</span></span>|<span data-ttu-id="7498c-516">Int16</span><span class="sxs-lookup"><span data-stu-id="7498c-516">Int16</span></span>|
|<span data-ttu-id="7498c-517">REMARKS</span><span class="sxs-lookup"><span data-stu-id="7498c-517">REMARKS</span></span>|<span data-ttu-id="7498c-518">String</span><span class="sxs-lookup"><span data-stu-id="7498c-518">String</span></span>|
|<span data-ttu-id="7498c-519">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="7498c-519">OVERLOAD</span></span>|<span data-ttu-id="7498c-520">Int32</span><span class="sxs-lookup"><span data-stu-id="7498c-520">Int32</span></span>|
|<span data-ttu-id="7498c-521">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="7498c-521">ORDINAL_POSITION</span></span>|<span data-ttu-id="7498c-522">Int32</span><span class="sxs-lookup"><span data-stu-id="7498c-522">Int32</span></span>|

### <a name="procedureparameters"></a><span data-ttu-id="7498c-523">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="7498c-523">ProcedureParameters</span></span>

|<span data-ttu-id="7498c-524">ColumName</span><span class="sxs-lookup"><span data-stu-id="7498c-524">ColumnName</span></span>|<span data-ttu-id="7498c-525">DataType</span><span class="sxs-lookup"><span data-stu-id="7498c-525">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="7498c-526">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="7498c-526">PROCEDURE_CAT</span></span>|<span data-ttu-id="7498c-527">String</span><span class="sxs-lookup"><span data-stu-id="7498c-527">String</span></span>|
|<span data-ttu-id="7498c-528">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="7498c-528">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="7498c-529">String</span><span class="sxs-lookup"><span data-stu-id="7498c-529">String</span></span>|
|<span data-ttu-id="7498c-530">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="7498c-530">PROCEDURE_NAME</span></span>|<span data-ttu-id="7498c-531">String</span><span class="sxs-lookup"><span data-stu-id="7498c-531">String</span></span>|
|<span data-ttu-id="7498c-532">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="7498c-532">COLUMN_NAME</span></span>|<span data-ttu-id="7498c-533">String</span><span class="sxs-lookup"><span data-stu-id="7498c-533">String</span></span>|
|<span data-ttu-id="7498c-534">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="7498c-534">COLUMN_TYPE</span></span>|<span data-ttu-id="7498c-535">Int16</span><span class="sxs-lookup"><span data-stu-id="7498c-535">Int16</span></span>|
|<span data-ttu-id="7498c-536">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7498c-536">DATA_TYPE</span></span>|<span data-ttu-id="7498c-537">Int16</span><span class="sxs-lookup"><span data-stu-id="7498c-537">Int16</span></span>|
|<span data-ttu-id="7498c-538">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="7498c-538">TYPE_NAME</span></span>|<span data-ttu-id="7498c-539">String</span><span class="sxs-lookup"><span data-stu-id="7498c-539">String</span></span>|
|<span data-ttu-id="7498c-540">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="7498c-540">COLUMN_SIZE</span></span>|<span data-ttu-id="7498c-541">Int32</span><span class="sxs-lookup"><span data-stu-id="7498c-541">Int32</span></span>|
|<span data-ttu-id="7498c-542">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="7498c-542">BUFFER_LENGTH</span></span>|<span data-ttu-id="7498c-543">Int32</span><span class="sxs-lookup"><span data-stu-id="7498c-543">Int32</span></span>|
|<span data-ttu-id="7498c-544">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="7498c-544">DECIMAL_DIGITS</span></span>|<span data-ttu-id="7498c-545">Int16</span><span class="sxs-lookup"><span data-stu-id="7498c-545">Int16</span></span>|
|<span data-ttu-id="7498c-546">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="7498c-546">NUM_PREC_RADIX</span></span>|<span data-ttu-id="7498c-547">Int16</span><span class="sxs-lookup"><span data-stu-id="7498c-547">Int16</span></span>|
|<span data-ttu-id="7498c-548">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="7498c-548">NULLABLE</span></span>|<span data-ttu-id="7498c-549">Int16</span><span class="sxs-lookup"><span data-stu-id="7498c-549">Int16</span></span>|
|<span data-ttu-id="7498c-550">REMARKS</span><span class="sxs-lookup"><span data-stu-id="7498c-550">REMARKS</span></span>|<span data-ttu-id="7498c-551">String</span><span class="sxs-lookup"><span data-stu-id="7498c-551">String</span></span>|
|<span data-ttu-id="7498c-552">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="7498c-552">COLUMN_DEF</span></span>|<span data-ttu-id="7498c-553">String</span><span class="sxs-lookup"><span data-stu-id="7498c-553">String</span></span>|
|<span data-ttu-id="7498c-554">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7498c-554">SQL_DATA_TYPE</span></span>|<span data-ttu-id="7498c-555">Int16</span><span class="sxs-lookup"><span data-stu-id="7498c-555">Int16</span></span>|
|<span data-ttu-id="7498c-556">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="7498c-556">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="7498c-557">Int16</span><span class="sxs-lookup"><span data-stu-id="7498c-557">Int16</span></span>|
|<span data-ttu-id="7498c-558">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="7498c-558">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="7498c-559">Int32</span><span class="sxs-lookup"><span data-stu-id="7498c-559">Int32</span></span>|
|<span data-ttu-id="7498c-560">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="7498c-560">ORDINAL_POSITION</span></span>|<span data-ttu-id="7498c-561">Int32</span><span class="sxs-lookup"><span data-stu-id="7498c-561">Int32</span></span>|
|<span data-ttu-id="7498c-562">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="7498c-562">IS_NULLABLE</span></span>|<span data-ttu-id="7498c-563">String</span><span class="sxs-lookup"><span data-stu-id="7498c-563">String</span></span>|

## <a name="see-also"></a><span data-ttu-id="7498c-564">Vea también</span><span class="sxs-lookup"><span data-stu-id="7498c-564">See also</span></span>

- [<span data-ttu-id="7498c-565">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="7498c-565">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
