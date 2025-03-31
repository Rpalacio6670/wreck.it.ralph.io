# wreck.it.ralph.io
Hello Wolrd!!
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Project Submission Dashboard</title>
    <style>
        body { font-family: Arial, sans-serif; margin: 40px; }
        .status { padding: 10px; border-radius: 5px; margin-bottom: 10px; }
        .success { background-color: #d4edda; color: #155724; }
        .error { background-color: #f8d7da; color: #721c24; }
        .pending { background-color: #fff3cd; color: #856404; }
    </style>
</head>
<body>

    <h2>Project Submission Dashboard</h2>
    
    <h3>✅ Folder Structure</h3>
    <div id="folderStatus" class="status success">All required folders are in place.</div>

    <h3>📂 Uploaded Files</h3>
    <ul id="fileList">
        <li>index.html ✅</li>
        <li>style.css ✅</li>
        <li>script.js ✅</li>
        <li>README.md ✅</li>
    </ul>

    <h3>🛠️ Validation Status</h3>
    <div id="validationStatus" class="status success">All files have been validated successfully.</div>

    <h3>📌 Submission Status</h3>
    <div id="submissionStatus" class="status success">Project files have been submitted to the Assignments Folder.</div>

    <h3>🔗 Project URL</h3>
    <a id="projectLink" href="http://aloft.server/~user/ProjectName/" target="_blank">View Project</a>
    <div id="urlStatus" class="status pending">Checking link...</div>

    <script>
        function checkURL() {
            let urlStatus = document.getElementById("urlStatus");
            fetch("http://aloft.server/~user/ProjectName/")
                .then(response => {
                    if (response.ok) {
                        urlStatus.innerHTML = "Project link is working correctly! ✅";
                        urlStatus.classList.remove("pending");
                        urlStatus.classList.add("success");
                    } else {
                        urlStatus.innerHTML = "Error: Project link is not accessible. ❌";
                        urlStatus.classList.remove("pending");
                        urlStatus.classList.add("error");
                    }
                })
                .catch(() => {
                    urlStatus.innerHTML = "Error: Project link is broken. ❌";
                    urlStatus.classList.remove("pending");
                    urlStatus.classList.add("error");
                });
        }
        window.onload = checkURL;
    </script>

</body>
</html>
