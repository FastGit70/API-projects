# API-YouTube Transcript to Word
Collected API projects; updated frequently

Backend: Python (FastAPI)
YouTube Transcript Extraction: youtube-transcript-api
DOCX File Generation: python-docx
Serving the DOCX file: FastAPI file response



Install the required Python packages
pip install fastapi uvicorn youtube-transcript-api python-docx


To run the API
uvicorn main:app --reload


Optional Cleanup
After sending the file, you can delete it if you don't want to store files on the server:

Add to the end of the function:
import threading
import time

# Delete file after some time
def cleanup(file_path):
    time.sleep(10)
    os.remove(file_path)

threading.Thread(target=cleanup, args=(file_path,)).start()
