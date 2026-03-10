# Music Student Portal 🎵

An application for music teachers to create and share lesson plans with their students digitally.

## Overview of features

- **Role-based authentication**: Two types of accounts exist: teacher and student. A teacher can create and view students and their lesson plans, as well as create new lessons for any of their students. A student can create an account tied to their teacher, and only see their own lesson plans.
- **Teacher Dashboard**: A teacher can see all students in their roster, clicking through to see that student's lessons.
- **Student Management**: A teacher can add and remove students from their roster.
- **Lesson Planning**: A teacher can create lesson plans with the date, content, and learning objectives.
- **Student view**: A student can log in and view all of their lessons from their teacher.

## 🛠️ Tech Stack

**Frontend**

- **EJS**: Templating engine for dynamic rendering of HTML server-side, based on backend data.

**Backend**

- **Node.js & Express**: Server and API routes.
- **MongoDB & Mongoose**: NoSQL database
- **Passport.js**: Authentication middleware.

## Getting Started

### Prerequisites

- Node.js installed
- MongoDB installed locally or a MongoDB Atlas URI

### Installation

1.  **Clone the repository**

    ```bash
    git clone https://github.com/DevinCLane/music-student-portal.git
    cd music-student-portal
    ```

2.  **Install dependencies**

    ```bash
    npm install
    ```

3.  **Configuration**
    Create a `.env` file in the `config` folder and add the following variables:

    ```env
    PORT=2121
    DB_STRING=your_mongodb_connection_string
    CLOUD_NAME=your_cloudinary_cloud_name
    API_KEY=your_cloudinary_api_key
    API_SECRET=your_cloudinary_api_secret
    ```

4.  **Run the application**
    ```bash
    npm start
    ```
    Open your browser and navigate to `http://localhost:2121`.

## Select API Routes

### Teacher Dashboard

| Method | Path                  | Description                                    |
| :----- | :-------------------- | :--------------------------------------------- |
| `GET`  | `/teachers/dashboard` | View teacher's dashboard with list of students |

### Student Management

| Method   | Path                            | Description                     |
| :------- | :------------------------------ | :------------------------------ |
| `GET`    | `/teachers/students/new`        | Form to add a new student       |
| `POST`   | `/teachers/students`            | Create a new student            |
| `GET`    | `/teachers/students/:studentId` | View individual student profile |
| `DELETE` | `/teachers/students/:studentId` | Delete a student                |

### Lesson Management

| Method | Path                                            | Description                 |
| :----- | :---------------------------------------------- | :-------------------------- |
| `GET`  | `/teachers/student/:studentId/lesson/new`       | Form to create a new lesson |
| `POST` | `/teachers/student/:studentId/lesson`           | Save a new lesson           |
| `GET`  | `/teachers/student/:studentId/lesson/:lessonId` | View individual lesson      |

## 🌟 Future Improvements

- **Multimedia uploads**: Upload and attach images (sheet music, diagrams, handwritten notes) to lessons using Cloudinary integration.
- **Markdown editor**: Compose and edit lessons in markdown to easily add line breaks, formatting, bold/italics, bullets/numbered lists, and links
- **Scheduling**: Integrated calendar for booking lessons.
- **Practice Logs**: Feature for students to record their practice time.
- **Billing**: Automated billing for teachers to bill students and their parents.
