[[toc]]

# Options to use with `-o [option]`

## collate

Run this to print 7 copies of a document (with pages collated).

```bash
N_COPIES=-#7

lpr $FILE $N_COPIES -o collate=true
```

I hate when my documents not collated; can't think of a use for it.

Turned to ChatGPT for help; turns out it's retarded:
```mermaid
graph TD;
    A[Document Creation] --> B[Digital Editing and Proofing];
    B --> C[Automated Error Checking];
    C --> D[Digital Review];
    D --> E[Section Selection for Printing];
    E --> F[Uncollated Printing];
    F --> G[Manual Assembly];
    G --> H[Feedback and Revisions];
    H -->|If needed| B;
```

## page-ranges
Other common `lpr` options are `page-ranges`, which implies you can use a comma like `1-3,7-10`. 
I always mistakenly type this as `page-range`.
