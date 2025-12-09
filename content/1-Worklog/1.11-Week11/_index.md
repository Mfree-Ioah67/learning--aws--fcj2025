---
title: "Week 11 Worklog"
date: 2025-11-17
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---

### Week 11 Objectives:

- Develop frontend with React and Vite
- Implement user interface components
- Integrate frontend with backend APIs
- Deploy frontend to S3 and CloudFront

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
|-----|------|------------|-----------------|-------------------|
| 1-3 | - Design UI/UX mockups <br> - Create React components <br>&emsp; + Login/Register pages <br>&emsp; + Dashboard <br>&emsp; + Blood donation form <br>&emsp; + Donor search <br> - Implement routing with React Router | 2025/11/17 | 2025/11/19 | React docs, Material-UI |
| 4-5 | - Integrate with backend APIs <br>&emsp; + Axios for HTTP requests <br>&emsp; + JWT token management <br>&emsp; + API error handling <br> - Test user flows end-to-end | 2025/11/20 | 2025/11/21 | Axios documentation |
| 6-7 | - Build production bundle <br> - Deploy to S3 <br>&emsp; + Configure S3 for static hosting <br>&emsp; + Upload dist files <br> - Set up CloudFront CDN <br> - Test deployed application | 2025/11/22 | 2025/11/23 | AWS S3, CloudFront docs |

### Week 11 Achievements:

- **Frontend Development:**
  - Designed clean and responsive UI with Material-UI
  - Created reusable React components
  - Implemented authentication pages (Login, Register)
  - Built dashboard with blood donation statistics
  - Developed blood donation request form
  - Created donor search with filters (blood type, location)
  - Implemented React Router for navigation

- **API Integration:**
  - Configured Axios for API calls
  - Implemented JWT token storage in localStorage
  - Created API service layer for clean code organization
  - Added loading states and error handling
  - Tested complete user flows: Register → Login → Create Donation → Search Donors

- **Frontend Deployment:**
  - Built optimized production bundle with Vite: `npm run build`
  - Configured S3 bucket for static website hosting
  - Uploaded dist files to S3 using AWS CLI
  - Set up CloudFront distribution for CDN
  - Configured custom domain (optional)
  - Verified application working on CloudFront URL

### Challenges Encountered:

- **CORS Issues:** Backend blocking frontend requests → Configured CORS in Spring Boot
- **State Management:** Complex state across components → Used React Context API
- **CloudFront Caching:** Old files being served → Created invalidation for `/*`

### Key Learnings:

- Mastered React hooks (useState, useEffect, useContext)
- Understood frontend-backend integration patterns
- Learned S3 static hosting and CloudFront CDN setup

### References:

- [React Documentation](https://react.dev/)
- [Vite Build Tool](https://vitejs.dev/)
- [AWS S3 Static Hosting](https://docs.aws.amazon.com/s3/static-website/)
- [CloudFront CDN](https://docs.aws.amazon.com/cloudfront/)
