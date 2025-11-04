Cell 8 (updates)
Core backend helpers consolidated: ingestion pipeline, chunking strategy, embedding calls, FAISS index handling, retrieval, RAG-answer assembly.
Persistence helpers expanded: save/load state, directory conventions for storing indexes and metadata.
Improved error handling, API sanity checks, and global state containers (DOCUMENTS, model defaults).

Cell 9 (updates / moved to cell9.py)
Gradio UI and event handlers (ingest, ask, Drive mount/save/load) packaged as a standalone file; UI improvements for document selection and better logging.

Cell 10
Document normalization: cleaned and standardized input text (Unicode, whitespace, simple OCR fixes) before chunking.

Cell 11
Chunking enhancements: configurable chunk size/overlap, sentence-aware splits, and token-count based chunking for consistent embeddings.
Cell 12
Per-document vector store management: create/load a separate FAISS index (and metadata files) per document or logical collection; folder layout conventions for indexes and metadata.

Cell 13
Batch embedding & rate-control: batched embedding calls with retry/backoff logic and optional parallelism to improve throughput and handle API limits.

Cell 14
Metadata and citation support: store source/file offsets, chunk IDs, and human-friendly citations for use in RAG outputs.

Cell 15
Retrieval improvements: hybrid filtering (by document IDs), configurable Top-K, and basic scoring/post-processing to prefer higher-quality chunks.

Cell 16
State management & export: functions to export/import full project state (indexes, docs, metadata) and lightweight snapshots suitable for Google Drive persistence.

Cell 17
Utilities, testing & debug helpers: quick QA checks, ingestion summary reports, verbose logging toggle, and small diagnostic endpoints to inspect index contents and sample embeddings.


Overall workflow impact

More robust ingestion (clean → chunk → batch-embed → per-doc index).
Better retrieval (document-scoped searches, metadata-aware citations).
Reliable persistence (clear folder layout, save/load/export to Drive).
Scalable embedding (batching, retries, rate control) and clearer debugging/logging. 
