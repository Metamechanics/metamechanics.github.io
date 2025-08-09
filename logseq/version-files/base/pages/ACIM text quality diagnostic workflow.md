alias::
tags:: #claude-ai
url::
rel-projects:: [[ACIM accordance]]
see-also::

-
- # ACIM Text Quality Diagnostic Workflow - Using Anthropic Console Credits
- ## 🎯 Credit Usage Strategy: Text Quality Diagnosis & Cleanup
- ### Goal:
	- Systematically identify and fix textual, grammatical, punctuation, and formatting flaws in your processed ACIM content
- ### Approach:
	- Use console credits for high-value diagnostic analysis that improves your entire processing pipeline

	  ---
- ## 📋 Step-by-Step Implementation Guide
- ### Step 1: Prepare Your Sample Content (5 minutes)
- #### What to Gather:
- 10-15 processed markdown files that show your "persistent error patterns"
- Mix of content types: Text chapters, Workbook lessons, review lessons
- Known problematic sections: Files where you've noticed issues
- Representative samples: Both "good" and "problematic" examples
- #### File Selection Criteria:
  ```
  Priority 1: Files with known formatting issues
  Priority 2: Files with review lesson parenthesis problems
  Priority 3: Files with superscript numbering issues
  Priority 4: Files with paragraph numbering problems
  Priority 5: Files with unicode/special character issues
  ```
- #### Recommended Sample Set:
- 3-4 Text chapter sections (various complexity levels)
- 3-4 Regular Workbook lessons
- 3-4 Review lessons (especially 171-180, 201-220 range)
- 2-3 Review introductions or special content
- ### Step 2: Access Anthropic Console
- #### How to Access:
  1. Go to: console.anthropic.com
  2. Log in with your Anthropic account
  3. Navigate to: Claude interface (not Workbench - use the chat interface)
  4. Verify credits: Check your remaining balance
- #### File Upload Method:
- In Claude console chat: Use the paperclip/attachment icon
- File formats supported: .md, .txt, .html (your markdown files will work)
- Upload limit: Multiple files per conversation
- Best practice: Upload 3-5 files at a time for focused analysis

  ---
- ## 🔍 Step 3: Diagnostic Analysis Prompts
- ### Phase 1: Pattern Recognition (Use ~25% of credits)
- #### Initial Diagnostic Prompt:
  ```
  I'm developing an ACIM text processor and need help identifying quality issues in my output. I've uploaded several processed ACIM sections that show my current "persistent error patterns."

  Please analyze these files and identify:

  1. Formatting Issues:
   - Paragraph numbering problems (should be 1. 2. 3.)
   - Sentence superscript issues (should be ¹²³⁴⁵⁶⁷⁸⁹⁰)
   - Inconsistent header formatting

  2. Content Integrity Problems:
   - Missing or duplicated sentences
   - Incomplete paragraphs
   - Orphaned numbers or fragments
   - Sequential numbering gaps

  3. ACIM-Specific Standards:
   - Theological term capitalization inconsistencies
   - Reference formatting problems (T-6.V.A.1:2, W-pI.182, etc.)
   - Special character issues (unicode, pipes, ellipses)

  4. Grammar & Punctuation:
   - Missing punctuation
   - Inconsistent quotation marks
   - Capitalization errors

  For each issue type, please:
  - Provide specific examples from the uploaded files
  - Suggest the correct format
  - Identify patterns that could be fixed systematically

  Focus on issues that appear across multiple files - these are my "persistent patterns" to fix.
  ```
- #### Follow-up Analysis Prompts:
  ```
  Based on your analysis, what are the top 5 most critical issues to fix first?

  For each critical issue, can you suggest:
  1. A specific search-and-replace pattern to fix it
  2. A processor rule to prevent it in future processing
  3. Examples of the before/after correction
  ```
- ### Phase 2: Specific Issue Deep-Dive (Use ~30% of credits)
- #### Focused Problem Analysis:
  Upload your most problematic files and ask:

  ```
  I'm particularly struggling with [SPECIFIC ISSUE - e.g., "review lesson parenthesis problems"].

  Looking at the uploaded files, can you:
  1. Identify the exact pattern causing this issue
  2. Show me what the correct format should be
  3. Provide a systematic way to fix all instances
  4. Suggest processor improvements to prevent this

  Please be very specific with examples and corrections.
  ```
- #### Common Specific Issues to Analyze:
- Review lesson parenthesis: "(182) ) I will be still..." → "(182) I will be still..."
- Superscript numbering: Missing or incorrect sequence
- Paragraph fragments: Incomplete content extraction
- Unicode issues: Smart quotes, ellipses, em-dashes
- Cross-reference formatting: Inconsistent lesson number formats
- ### Phase 3: Correction Validation (Use ~25% of credits)
- #### Test Your Fixes:
  After implementing Claude's suggestions, upload corrected samples:

  ```
  I've implemented your suggested fixes for [SPECIFIC ISSUES].

  Please analyze these corrected files and verify:
  1. Are the issues properly resolved?
  2. Have I introduced any new problems?
  3. Is the formatting now consistent with ACIM standards?
  4. Any remaining quality concerns?

  Please give me a quality score (1-10) for each file and overall assessment.
  ```
- ### Phase 4: Batch Quality Check (Use remaining ~20% credits)
- #### Final Quality Assurance:
  ```
  Please perform a comprehensive quality check on these processed ACIM sections:

  1. Structural Integrity: Proper numbering, complete content
  2. ACIM Standards: Correct theological formatting
  3. Professional Polish: Grammar, punctuation, consistency
  4. Metadata Accuracy: Verify word counts, section counts match content

  Provide a detailed quality report with:
  - Overall quality score (1-10)
  - Specific remaining issues
  - Recommendations for final polish
  - Readiness assessment for database integration
  ```

  ---
- ## 🛠 Step 4: Systematic Implementation
- ### Fix Application Process:
  1. Document Claude's findings in a quality issues spreadsheet
  2. Prioritize fixes by frequency and impact
  3. Test fixes on sample files before batch processing
  4. Apply corrections systematically across your corpus
  5. Validate improvements with follow-up Claude analysis
- ### Processor Improvement Integration:
  ```python
  # Example: Add Claude-suggested improvement to your processor
  def clean_review_parenthesis(text):
    # Claude identified this pattern: "(182) ) I will be still"
    # Fix to: "(182) I will be still"
    pattern = r'\((\d+)\)\s*\)\s*'
    replacement = r'(\1) '
    return re.sub(pattern, replacement, text)
  ```

  ---
- ## 💡 Credit Optimization Tips
- ### Maximize Value:
- Upload multiple related files per conversation to get comparative analysis
- Ask specific, focused questions rather than general requests
- Build on previous insights within the same conversation thread
- Request actionable solutions, not just problem identification
- ### Efficient Conversations:
- Keep conversations focused on 1-2 issue types at a time
- Provide context about your ACIM processing goals
- Ask for systematic solutions that scale across your corpus
- Request both fixes and prevention strategies
- ### Avoid Credit Waste:
- Don't upload entire large files - extract problematic sections
- Don't repeat the same analysis - build on previous insights
- Focus on systemic issues rather than one-off problems
- Ask for batch solutions rather than individual fixes

  ---
- ## 📊 Expected Outcomes
- ### After Phase 1 (Pattern Recognition):
- Clear inventory of your top 5-10 quality issues
- Specific examples of each problem type
- Systematic solutions for each issue category
- ### After Phase 2 (Deep-Dive Analysis):
- Targeted fixes for your most persistent problems
- Processor improvements to prevent future issues
- Quality standards for ACIM-specific formatting
- ### After Phase 3 (Validation):
- Verified improvements in text quality
- Confidence in your correction methods
- Quality metrics showing measurable progress
- ### After Phase 4 (Final QA):
- Publication-ready text quality
- Database-integration readiness
- Professional polish across your ACIM corpus

  ---
- ## 🎯 Quick Start Checklist
- ### Today:
- [ ] Select 10-15 representative problem files
- [ ] Access console.anthropic.com
- [ ] Upload first batch (3-5 files)
- [ ] Run initial diagnostic analysis prompt
- [ ] Document findings for systematic fixing
- ### This Week:
- [ ] Complete all 4 phases of analysis
- [ ] Implement top 3-5 critical fixes
- [ ] Test improvements on sample content
- [ ] Validate quality improvements with Claude
- [ ] Apply fixes systematically across corpus
- ### Success Metrics:
- Quality Score: Target 8-9/10 for processed sections
- Error Reduction: 80%+ reduction in persistent error patterns
- Consistency: Uniform formatting across all content types
- Database Readiness: Clean, structured text ready for concordance integration

  ---
- ## 🚀 Advanced Usage (If Credits Allow)
- ### Metadata Enhancement:
  ```
  Please analyze these ACIM sections and generate enhanced metadata including:
  - Key theological concepts
  - Difficulty level (beginner/intermediate/advanced)
  - Related sections for cross-referencing
  - Practice type (contemplative/active/foundational)
  ```
- ### Cross-Reference Generation:
  ```
  Please identify conceptual connections between these Text sections and Workbook lessons for concordance cross-referencing.
  ```
- ### Quality Standards Documentation:
  ```
  Based on your analysis, please create ACIM-specific quality standards I can use for future processing validation.
  ```

  This workflow will give you maximum value from your console credits while systematically improving your ACIM text quality from "good enough" to "publication ready."
