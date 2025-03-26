# note_service
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>학생 필기 공유 플랫폼</title>
    <link rel="stylesheet" href="styles.css">
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f5f6f7;
            color: #333;
            margin: 0;
            padding: 0;
        }
        .header {
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 20px;
            background: #03c75a;
            color: white;
            font-size: 24px;
        }
        .header h1 {
            margin: 0;
        }
        .profile-icon {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background-color: white;
            display: flex;
            justify-content: center;
            align-items: center;
            overflow: hidden;
        }
        .profile-icon img {
            width: 80%;
            height: 80%;
        }
        .container {
            max-width: 1000px;
            margin: 20px auto;
            padding: 20px;
        }
        .search-container {
            display: flex;
            justify-content: center;
            align-items: center;
            margin-bottom: 20px;
        }
        input[type="text"] {
            width: 60%;
            padding: 10px;
            border: 1px solid #ccc;
            border-radius: 5px;
        }
        .search-icon {
            width: 30px;
            height: 30px;
            margin-left: 10px;
            cursor: pointer;
        }
        .file-list {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            justify-content: center;
        }
        .file-item {
            background: #d9e5d6;
            padding: 10px;
            border-radius: 5px;
            text-align: center;
            width: 150px;
            cursor: pointer;
        }
        .community-container {
            display: flex;
            justify-content: space-between;
            gap: 20px;
            margin-top: 40px;
        }
        .community-box {
            width: 48%;
            background: #e3f2e1;
            padding: 15px;
            border-radius: 5px;
            position: relative;
        }
        .community-box h2 {
            background: #03c75a;
            color: white;
            padding: 10px;
            margin: -15px -15px 10px;
            border-radius: 5px 5px 0 0;
        }
        .add-button {
            position: absolute;
            top: 10px;
            right: 10px;
            background: white;
            border: none;
            font-size: 20px;
            cursor: pointer;
            color: #03c75a;
            border-radius: 50%;
            width: 30px;
            height: 30px;
            text-align: center;
        }
    </style>
</head>
<body>
    <script>
        // Create header
        const header = document.createElement('div');
        header.className = 'header';
        header.innerHTML = `
            <h1>필기공유 플랫폼</h1>
            <div class="profile-icon">
                <img src="프로필 그림.png" alt="Profile">
            </div>
        `;
        document.body.appendChild(header);

        // Create container
        const container = document.createElement('div');
        container.className = 'container';

        // Create file list
        const fileList = document.createElement('div');
        fileList.className = 'file-list';
        fileList.id = 'fileList';
        container.appendChild(fileList);

        // Create community container
        const communityContainer = document.createElement('div');
        communityContainer.className = 'community-container';

        // Create community box
        const communityBox = document.createElement('div');
        communityBox.className = 'community-box';
        communityBox.innerHTML = `
            <h2>커뮤니티</h2>
            <button class="add-button">+</button>
            <ul id="communityList"></ul>
        `;
        communityContainer.appendChild(communityBox);

        // Create Q&A box
        const qaBox = document.createElement('div');
        qaBox.className = 'community-box';
        qaBox.innerHTML = `
            <h2>질의응답</h2>
            <button class="add-button">+</button>
            <ul id="qaList"></ul>
        `;
        communityContainer.appendChild(qaBox);

        // Append community container to main container
        container.appendChild(communityContainer);
        document.body.appendChild(container);

        // File data
        let fileData = [
            { name: "필기노트", url: "https://example.com/notes" },
            { name: "레포트", url: "https://example.com/reports" },
            { name: "시험정보", url: "https://example.com/exams" },
            { name: "스터디그룹", url: "https://example.com/study" }
        ];

        // Function to display files
        function displayFiles() {
            const fileList = document.getElementById("fileList");
            fileList.innerHTML = "";
            fileData.forEach(file => {
                const div = document.createElement("div");
                div.classList.add("file-item");
                div.textContent = file.name;
                div.onclick = () => window.location.href = file.url;
                fileList.appendChild(div);
            });
        }

        // Display files
        displayFiles();
    </script>
</body>
</html>
