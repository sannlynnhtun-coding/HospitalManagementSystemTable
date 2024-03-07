# Hospital Management System Table

```sql
USE [HospitalManagementSystem]
GO
/****** Object:  Table [dbo].[Tbl_Appointment]    Script Date: 2024-03-07 9:00:54 PM ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[Tbl_Appointment](
	[AppointmentId] [varchar](50) NOT NULL,
	[PatientId] [varchar](50) NOT NULL,
	[DoctorId] [varchar](50) NOT NULL,
	[AppointmentDate] [datetime] NOT NULL,
	[RoomId] [varchar](50) NOT NULL,
	[TokenId] [varchar](50) NOT NULL,
	[Status] [varchar](50) NOT NULL,
	[IsCancel] [bit] NOT NULL,
 CONSTRAINT [PK_Tbl_Appointment] PRIMARY KEY CLUSTERED 
(
	[AppointmentId] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON, OPTIMIZE_FOR_SEQUENTIAL_KEY = OFF) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[Tbl_Disease]    Script Date: 2024-03-07 9:00:54 PM ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[Tbl_Disease](
	[DiseaseId] [varchar](50) NOT NULL,
	[DiseaseName] [nvarchar](50) NOT NULL,
 CONSTRAINT [PK_Tbl_Disease] PRIMARY KEY CLUSTERED 
(
	[DiseaseId] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON, OPTIMIZE_FOR_SEQUENTIAL_KEY = OFF) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[Tbl_Doctor]    Script Date: 2024-03-07 9:00:54 PM ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[Tbl_Doctor](
	[DoctorId] [nvarchar](50) NOT NULL,
	[DoctorName] [nvarchar](50) NOT NULL,
	[Email] [nvarchar](50) NOT NULL,
	[MobileNo] [nvarchar](50) NOT NULL,
	[Position] [nvarchar](50) NOT NULL,
	[AvailableStartHour] [int] NOT NULL,
	[AvailableEndHour] [int] NOT NULL,
 CONSTRAINT [PK_Tbl_Doctor] PRIMARY KEY CLUSTERED 
(
	[DoctorId] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON, OPTIMIZE_FOR_SEQUENTIAL_KEY = OFF) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[Tbl_DoctorSpecialistId]    Script Date: 2024-03-07 9:00:54 PM ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[Tbl_DoctorSpecialistId](
	[DoctorSpecialistId] [varchar](50) NOT NULL,
	[DoctorId] [varchar](50) NOT NULL,
	[DiseaseId] [varchar](50) NOT NULL,
 CONSTRAINT [PK_Tbl_DoctorSpecialistId] PRIMARY KEY CLUSTERED 
(
	[DoctorSpecialistId] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON, OPTIMIZE_FOR_SEQUENTIAL_KEY = OFF) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[Tbl_MedicalRecord]    Script Date: 2024-03-07 9:00:54 PM ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[Tbl_MedicalRecord](
	[MedicalRecordId] [varchar](50) NOT NULL,
	[PatientId] [varchar](50) NOT NULL,
	[DiseaseId] [varchar](50) NOT NULL,
	[StartDate] [datetime] NOT NULL,
 CONSTRAINT [PK_Tbl_MedicalRecord] PRIMARY KEY CLUSTERED 
(
	[MedicalRecordId] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON, OPTIMIZE_FOR_SEQUENTIAL_KEY = OFF) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[Tbl_Patient]    Script Date: 2024-03-07 9:00:54 PM ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[Tbl_Patient](
	[PatientId] [nvarchar](50) NOT NULL,
	[PatientName] [nvarchar](50) NOT NULL,
	[DateOfBirth] [datetime] NOT NULL,
	[Blood] [varchar](2) NOT NULL,
	[Gender] [varchar](10) NOT NULL,
	[MobileNo] [varchar](50) NOT NULL,
	[Email] [nvarchar](50) NOT NULL,
	[Address] [nvarchar](500) NOT NULL,
 CONSTRAINT [PK_Tbl_Patient] PRIMARY KEY CLUSTERED 
(
	[PatientId] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON, OPTIMIZE_FOR_SEQUENTIAL_KEY = OFF) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[Tbl_Record]    Script Date: 2024-03-07 9:00:54 PM ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[Tbl_Record](
	[RecordId] [varchar](50) NOT NULL,
	[DoctorId] [varchar](50) NOT NULL,
	[PatientId] [varchar](50) NOT NULL,
	[StartDateTime] [datetime] NOT NULL,
	[EndDateTime] [datetime] NOT NULL,
	[RoomId] [varchar](50) NOT NULL,
	[Fees] [decimal](20, 0) NOT NULL,
	[Remark] [nvarchar](250) NULL,
 CONSTRAINT [PK_Tbl_Record] PRIMARY KEY CLUSTERED 
(
	[RecordId] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON, OPTIMIZE_FOR_SEQUENTIAL_KEY = OFF) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[Tbl_Room]    Script Date: 2024-03-07 9:00:54 PM ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[Tbl_Room](
	[RoomId] [nvarchar](50) NOT NULL,
	[RoomName] [nvarchar](50) NOT NULL
) ON [PRIMARY]
GO
```
