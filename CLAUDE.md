# agentic-coe: standing instructions

**This repository is public.** It's Mario's public-facing body of work,
frameworks, tools, and templates drawn from 623+ case studies, 65+
practitioner interviews, and direct enterprise delivery experience (see
`README.md`). Anything committed here is visible to anyone.

## Hard rule: no exceptions

**Never commit, or help commit, client names, company names, named
individuals, or other confidential/identifying information to this
repository.** This applies to every file, every commit, every PR, code,
docs, examples, case-study writeups, everything. If a change is about to
introduce a real client/company name or an identifying specific, stop and
flag it rather than writing it, even if the source material (an
interview, a transcript, a client engagement) is real and Mario's own.

This is not a style preference, it's a standing instruction. Treat it
with the same weight as a security boundary.

## The sanitization checklist

Before anything derived from real client/practitioner material goes into
this repo, it needs to pass all four:

1. **Client/company name → vertical + size descriptor** ("a regional
   health system, ~8,000 employees")
2. **Named individuals → role only** (CIO, VP Data, Practitioner)
3. **Identifying specifics removed or generalized**: product names,
   contract values, exact dates precise enough to identify an engagement
4. **Confirm the pattern still holds without the identifying detail**,
   if the point only works with the client named, it isn't publishable
   here; it needs more generalization, or it doesn't belong in this repo

This is the same discipline already documented in `mario-ai-lab`'s
`library/catalog.md` ("Before anything from here goes public"), applied
here at the point of publication. If you're bringing material over from
`mario-ai-lab`, `mario-dev/kb/`, a Plaud transcript, or any other private
source, run it through that checklist first, don't assume upstream
material is already safe just because it exists in a private repo.

**The test, same as `mario-ai-lab`'s**: if this file/commit became fully
public tomorrow (it already is), could anyone identify the client? If
yes, it's over-specified, fix it before committing, not after.
