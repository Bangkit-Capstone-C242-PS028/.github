# DermaScan

# About this project

In Indonesia, many underserved communities struggle to access basic healthcare, especially for early diagnosis and treatment of skin conditions. Limited access to dermatologists and healthcare facilities makes it difficult for individuals in these areas to receive timely care, which often leads to delayed treatment and worsened health outcomes. Traditional diagnostic tools rely on large amounts of data and skilled professionals, which are often unavailable or inaccessible in these regions.

To address these challenges, an accessible and reliable digital health solution is needed to provide early detection, remote consultation, and educational health resources. By leveraging AI-driven skin lesion classification, telehealth features, and accessible information, this project seeks to empower underserved communities with a tool that can improve their health and well-being, regardless of geographic or economic limitations.

The increasing prevalence of dermatological diseases, combined with the diversity and rarity of certain skin lesions, presents a significant diagnostic challenge in dermatology. Traditional diagnostic methods struggle with accuracy, particularly when data for rare conditions is limited, which can delay proper treatment and worsen patient outcomes.

Empower your skin health journey with DermaScan! 🌟🩺 This innovative app is your personalized guide to healthy skin, providing AI-driven skin lesion classification, remote consultations with dermatologists, and valuable educational resources. Take charge of your skin health and ensure timely care and treatment, no matter where you are. 🌍✨

# Team Member - C242-PS028

<div align="center">

|  Bangkit ID  | Name                       |   Learning Path    |                      LinkedIn Profile                       | Github                                               | Status |
| :----------: | -------------------------- | :----------------: | :---------------------------------------------------------: | ---------------------------------------------------- | :----- |
| A179B4KY2165 | Kemas Khairunsyah          | Mobile Development |  [LinkedIn](https://www.linkedin.com/in/kemaskhairunsyah/)  | [@herros27](https://github.com/herros27)             | Active |
| A284B4KY3690 | Rangga Gumilang            | Mobile Development |     [LinkedIn](https://www.linkedin.com/in/ranggagum/)      | [@ranggagumilang](https://github.com/ranggagumilang) | Active |
| M008B4KY0003 | A.A. Gde Yogi Pramana      |  Machine Learning  |      [LinkedIn](https://www.linkedin.com/in/yogiprmn/)      | [@IgoyAI](https://github.com/IgoyAI)                 | Active |
| M008B4KY0058 | Achmad Husein              |  Machine Learning  |    [LinkedIn](https://www.linkedin.com/in/achmadhusein/)    | [@achuseinn](https://github.com/achuseinn)           | Active |
| M008B4KY2962 | Muhammad Naufal Musyaffa   |  Machine Learning  | [LinkedIn](https://www.linkedin.com/in/naufal-m-6b53a0169/) | [@NaufalM479](https://github.com/NaufalM479)         | Active |
| C008B4KY2936 | Muhammad Luthfi Harwidjaya |  Cloud Computing   |     [LinkedIn](https://www.linkedin.com/in/luthfiharw/)     | [@harwHarw03](https://github.com/harwHarw03)         | Active |
| C008B4KY3798 | Rhafael Chandra            |  Cloud Computing   |      [LinkedIn](https://www.linkedin.com/in/rhafaelc/)      | [@rhafaelc](https://github.com/rhafaelc)             | Active |

</div>

# Mobile Development

TODO

# Machine Learning

TODO

# Cloud Computing

## Project Architecture

<div align="center">
  <img src="https://raw.githubusercontent.com/Bangkit-Capstone-C242-PS028/.github/refs/heads/main/profile/assets/GCP%20Architecture%20DermaScan.png" alt="Cloud Architecture" style="width: 100%;">
</div>

## Database Diagram

```mermaid
erDiagram
    USER {
        string uid PK
        string role
        string email
        string firstName
        string lastName
        date dob
        string address
        date createdAt
        date updatedAt
        int points
        string photoUrl
    }

    DOCTOR {
        string uid PK
        string specialization
        string workplace
        string documentUrl
        bool isVerified
        string phoneNumber
    }

    PATIENT {
        string uid PK
    }

    ARTICLE {
        string id PK
        text title
        text content
        string imageUrl
        date created_at
        date updated_at
    }

    FAVORITE {
        string id PK
        date created_at
    }

    FORUM {
        string id PK
        text title
        text content
        string status
        date created_at
        date updated_at
    }

    FORUM_REPLY {
        string id PK
        string responder_role
        text content
        date created_at
        date updated_at
    }

    SKIN_LESION {
        string id PK
        string originalImageUrl
        string processedImageUrl
        enum status
        string classification
        string description
        date createdAt
        date processedAt
    }

    CONSULTATION {
        string id PK
        enum status
        date requestedAt
        date acceptedAt
        date completedAt
    }

    CONSULTATION_MESSAGE {
        string id PK
        string content
        date sentAt
    }

    ACTIVITY_LOG {
        string id PK
        string activity
        int points
        date createdAt
    }

    USER ||--o{ DOCTOR : "has one"
    USER ||--o{ PATIENT : "has one"
    USER ||--o{ FAVORITE : "has many"
    USER ||--o{ ACTIVITY_LOG : "has many"
    DOCTOR ||--o{ ARTICLE : "writes"
    DOCTOR ||--o{ CONSULTATION : "conducts"
    PATIENT ||--o{ CONSULTATION : "requests"
    PATIENT ||--o{ FORUM : "creates"
    PATIENT ||--o{ SKIN_LESION : "has many"
    ARTICLE ||--o{ FAVORITE : "is favorited"
    FORUM ||--o{ FORUM_REPLY : "has many"
    FORUM_REPLY ||--o{ USER : "is responded by"
    CONSULTATION ||--o{ CONSULTATION_MESSAGE : "has many"
    CONSULTATION_MESSAGE ||--o{ USER : "is sent by"
```

# Project Documentation

1. Learning Path Repository
   - [Mobile Development](https://github.com/Bangkit-Capstone-C242-PS028/MD)
   - [Machine Learning](https://github.com/Bangkit-Capstone-C242-PS028/ML)
   - Cloud Computing
     - [Main API (NestJS)](https://github.com/Bangkit-Capstone-C242-PS028/CC)
     - [Admin Dashboard (Next.js)](https://github.com/Bangkit-Capstone-C242-PS028/CC-ADMIN-WEB)
     - [ML API (Flask)](https://github.com/Bangkit-Capstone-C242-PS028/CC-PROCESS-IMAGE)
