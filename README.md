# AWS-Learnings

<img src="./src/aws_overview.png"/>

<img src="./src/aws_zones.png"/>

<img src="./src/aws_partioning.png"/>


# What is AWS?

AWS stands for Amazon Web Services, a cloud computing platform provided by Amazon.

It lets individuals and companies rent computing resources over the internet instead of buying and maintaining physical servers.

## What AWS provides

AWS offers hundreds of cloud services, including:

* **Compute** – virtual servers and app hosting
  Example: EC2, Lambda

* **Storage** – store files, backups, and databases
  Example: S3, EBS

* **Databases** – managed SQL and NoSQL databases
  Example: RDS, DynamoDB

* **Networking** – routing, DNS, content delivery
  Example: VPC, Route 53, CloudFront

* **AI & Machine Learning** – build and deploy AI models
  Example: SageMaker, Bedrock

* **Security** – identity management and encryption
  Example: IAM, KMS

## Simple analogy

Instead of buying:

* servers,
* networking hardware,
* storage devices,
* and data centers,

you “rent” them from AWS and pay only for what you use.

It’s similar to:

* using electricity from a utility company instead of running your own power plant.

## Why companies use AWS

Businesses use AWS because it offers:

* Scalability (grow or shrink instantly)
* Reliability
* Global infrastructure
* Pay-as-you-go pricing
* Security and compliance tools
* Faster deployment

<img src="./src/aws_benefits_1.png" alt="AWS Benefits"/>
<img src="./src/aws_benefits_2.png" alt="AWS Benefits"/>
<img src="./src/aws_benefits_3.png" alt="AWS Benefits"/>

<img src="./src/aws_support_overview.png" alt="AWS Support">
<img src="./src/aws_documentation.png" alt="AWS Documentation">
<img src="./src/aws_technical_resource.png" alt="AWS Technical Resources">
<img src="./src/aws_trusted_advisor.png" alt="AWS Trusted Advisor">


<img src="./src/aws_system_manager_overview.png" alt="AWS System Manager Overview">
<img src="./src/aws_system_manager_features.png" alt="AWS System Manager Features">
<img src="./src/aws_system_manager_use_cases.png" alt="AWS System Manager Use Cases">


## Common AWS services

Here are a few well-known services:

| Service    | Purpose                        |
| ---------- | ------------------------------ |
| EC2        | Virtual servers                |
| S3         | File/object storage            |
| Lambda     | Run code without servers       |
| RDS        | Managed relational databases   |
| CloudFront | CDN/content delivery           |
| IAM        | Access control and permissions |

## Who uses AWS?

Many major organizations use AWS, including startups, enterprises, governments, and streaming platforms.

Examples include:

* Netflix
* Airbnb
* NASA
* Samsung
* Twitch

## Example use case

A company building a website might use:

* **EC2** to run the website
* **RDS** for the database
* **S3** to store images
* **CloudFront** to deliver content globally


# AWS S3: Simple Storage Service

**Amazon S3 (Simple Storage Service)** is one of the core storage services in AWS. It lets you store and retrieve any amount of data from anywhere over the internet.

<img src="./src/s3/s3_overview.png" alt="S3 Overview"/>



## What S3 actually is

Think of S3 like a **highly durable online file storage system**.

* You upload files → AWS stores them
* You download files → anytime, from anywhere
* You don’t manage servers at all

In AWS terms:

* Files = **Objects**
* Folders = **Buckets**

## How it works (simple)

```
Bucket (like a folder)
   ├── image.jpg (object)
   ├── video.mp4 (object)
   └── data.json (object)
```

You create a **bucket**, then upload **objects** inside it.

## Key features

<img src="./src/s3/s3_features.png" alt="S3 Features"/>

### 1. Unlimited storage

You can store virtually **unlimited data**.

### 2. High durability

AWS promises **99.999999999% durability** (11 nines).
Your data is automatically replicated across multiple systems.

### 3. Access control

You control who can access files using:

* IAM policies
* Bucket policies
* Public/private access settings

### 4. Pay only for usage

You pay for:

* Storage used
* Data transfer
* Requests

### 5. Different storage classes

You can optimize cost:

| Class                | Use case                           |
| -------------------- | ---------------------------------- |
| Standard             | Frequently accessed data           |
| Intelligent-Tiering  | Auto cost optimization             |
| Glacier              | Archival (very cheap, slow access) |
| Glacier Deep Archive | Long-term backup                   |

## Common use cases

People use S3 for:

* Storing images/videos for websites
* Backups and disaster recovery
* Hosting static websites
* Data lakes for analytics
* Logs and application data

## Example

If you're building a web app:

* Upload user profile images → S3
* Store PDFs or documents → S3
* Backup database → S3

## Real-world analogy

S3 is like:

* **Google Drive**, but for developers
* **Dropbox**, but scalable for companies

## Important concepts

* **Bucket name must be globally unique**
* **Objects can be up to 5TB**
* You access objects via URLs

Example:

```
https://your-bucket-name.s3.amazonaws.com/image.jpg
```

## Quick example (AWS CLI)

Upload a file:

```bash
aws s3 cp file.txt s3://my-bucket/
```

Download a file:

```bash
aws s3 cp s3://my-bucket/file.txt .
```

## Storage Classes

Amazon S3 storage classes are basically **different pricing + performance tiers** for storing your data, depending on how often you access it and how quickly you need it.

Instead of using one type of storage for everything, AWS lets you optimize cost by choosing the right class.

<img src="./src/s3/s3_storage_class.png" alt="Storage Classes"/>

---

### Core idea

* Frequently used data → faster but expensive
* Rarely used data → cheaper but slower
* Archive data → very cheap but takes time to retrieve

---

### Main S3 storage classes

#### 1. S3 Standard (default)

![Image](https://images.openai.com/static-rsc-4/1_SQJPme64nKqNf1k15vYeerzVSFIfHtmA6NLQXDdPKb84AJFXnot-M7T72ralv2NpAxn87fH8hbb4klY_lMwQzOlK1GClw7pJAQ8b4R89Nb1F6mbdjnN-_w6Qw0DyKYWj6JNchTFLyNViI29H3X20y_6UNnP0XO_DXbxbrN1iDUKW8gG2HSOvF85wVVoVIR?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/Av-p5UcWkLN19ki7Jg2nzRr3995Hyc_1XjDxyCiyeh_03lR-SK99aOedNpjh0ZUZPxtRFBdCaDDTUOMBuwEuC95mUMtLs3Tl-iO1hp3of2q7PQnYIrBxH_RE9j9xihtr1Rr81y21n9WAZCEqVWwrIjuM0mtEj1uFMPULDmB5Zx_uBTzHoAVK45PNf7t8sx6_?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/KPCV3oY8De6OLpJs2PygKsUy3NFdi-Sx1DJ69dBYkghJz30nrq0WLNMa5lywPLcNqY0bPUzSZeIialt0KWKIl36F13TUePVjW8T4Lp_KPcO5NJZ_z_PG1e08De02hQl2XHyMuo-R5m5KBhXVE87vbUOTTm2dHFFcVH7B-uCa_ReBPgLDz8zBa6rKefgtNU2C?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/HTuZF7-OW-nD8P17rEYVryEVZtqKZS4yLuNqULIE_mfU2wCHMmTcx7C2lcgX5pkKnXFsVwh4lLmS18CWSHLraGhg6YQa_M5m2rWEbP4OY6AVKd7SMCQUkmva7zIEjEP-odB2qq460PwVNaun-L7LMBKZ_V_yeHraKD96QpP0-EhHKim5e_xXj3tuepiBzKrd?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/fVDF22-ugTlA43bhkbcTwYGTS7ZyFegcOTugg_I5VY86wBeMQRhmINDzbY4TKbChIuiSO2u6Jz4xDL99-vIcWA3ZgCB0_tXZ0Oq1xtRf9xDp4ypqeAmumOKVVFquKixPvFBj7tsmBnuywI9-zzcxi_BpF15M1g08M_nUQemv7sIXRWv4KqhGwEJ8-J1NXR4H?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/2q0DHG1WPdFK4NBP7oxyF-xpe9Qg54sqZMOelBmYG_vObGrG4B7Uf5pHPpPbtzORsbCwn0EN_ehnXpMxTEWGxOsOKcO8u8-xnaHLB1TloXy1_LLL9Be5TT6XvTWjDluGnWo-ZxINKrErIl1P9Z2osyT9-_CxdAlcyl55Nogl5C3gh9MvZqatbpmjtnmgD1Ld?purpose=fullsize)

* For frequently accessed data
* Low latency, high throughput
* Stored across multiple AZs

**Use case:**

* Websites
* Apps
* APIs
* Active data

---

#### 2. S3 Intelligent-Tiering

![Image](https://images.openai.com/static-rsc-4/peFltL2wV2blCEqGMvurHe1d_v95UJk0eN-FegXzXXlAodtBX4tlisaP7zZZab5Ky_TWlgUYEF_7R2e3X_DhpXwK2PS03Ohv7MgbPHdE-8beEz8YMDhvbkXJ1NLXcBFOdXVNfFzmquU0LanJ6kgv39alK8WoNYKKkQO5J9BcsxjxM7apaxwGhIiLw4bNN6u3?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/o62Fdotqqwl3XLOsOLhgPM2G5ur--5O5wnFUPS02DkC0gQpBBMHWylZz0NqJR5U2LEiYoDPs2jmWbEvrOh5bWpF8ch6MA_hsR0Q9a9M8az-BQoxcJLp1WzXGgwgVGHIrUNDxJXCucUUNcHkq-g-sLh27DM8uVB62DLKA0PAtZoJNFftNxt6d7A69AY9nNnD4?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/rTvY3uUk6W3FvtHOo6iEYctXW-MtrlEkMxudCNUYgEqhDkjWttftgyqFr81xFduMJJbuydCTufpK2Y-0Ahnd3Inr4HocRlSaHL5Xv1FFQDQ1PSXrf8-fY0RvlgeF9YhX0nq7FVYZaGRj5zuSM-iMmnCD2_W-AFRXdr8m_ruEH_It3H3ex-6PaeAjTNpVYS8e?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/yYW_9Oe8y1nFFgPhmiPb6YCdeKgcBkxY7A_PupaCgBOvBNLSjEyYYsRps6ocQuHIctMQ7WPAv3KHwU01zHouzv7vDaN-n1XA8cU_cqwg8NclWMcLUWWTtxmKyC5YEDNO-Zo75H0UZorGBCLlcilhbunIi7NL53sPwT7TjG0SsexLMWNa-vEv2I3jEbhAQnwL?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/Q6G-1N3aQ_QHNhr3OuYpuj_DsCri-KAHqBK6APPjEe6o91DKR3H31CpMg9TL41204dWeI_181ICKWb8EzJoVvruCi0FoFw3UNu-mPG21tkrqiE-wXoAfl45sqPgxJ9wYE-ktF3NOiVubVlRMd32aIxCufJk8GzuU4l3U5kTNqgX5Ay2Kk-0L0c96RD1vkuG_?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/QD6Oh3OK6Acmcf8djQGm-SWCtub11cqkRI4o8Np3IvszWXmw-pE44pKa4E8HL167kn-_JQt-xyj4Ih9QvRdTvnJNTtx1v-lJ4dDkSXbproBSxGIDYbDXS57Tdq5uw6J47wKYgoollisNz1slnexgavO1aJibGnpEdtudD1jDPlXagTipODS5NS2QLLBaFbPv?purpose=fullsize)

* Automatically moves data between tiers
* Best when access pattern is unknown

**Use case:**

* Unpredictable usage (logs, user uploads)

👉 You don’t need to think much—AWS optimizes cost for you.

---

#### 3. S3 Standard-IA (Infrequent Access)

![Image](https://images.openai.com/static-rsc-4/qEgrrBcegcQ5mfxqAQZ1Xs_D_SxexkYnIXnJ25n768cuvm7ADn2uE59Myx_ayS1Nj24cMZwASfOd0jLosBljtzi6_3gw9cO30HI-e8i85T68hXwdFtp8eCihrYlZXz8GiNC18Gbo5g9hCWYxofT6JPFzod7SOm4EmMQNSx9OrAu8YkInajU7DFz_f6_WFk5h?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/WYNvcgNTC6K73-_URXHQa83VAzs-M50lc2Vk0eVud82h4Evk4_V98s2KM9G88Dgz3EtHxHeQYMtEIiOCU-GaGXA2CmJ0JDOWpMRfaV3ERjHzKYdQfTCT4ImUL3W8TAZB7FaMi1mAW2bTYJkvC4ZgrIJkAVppH6QuEsgnD5ykxGzeiXVF8QkWw5DDgwR40i_0?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/jtddL5mo_1Oa5hlph1GYC2vRd7lQx0MbNEH-SJNqgUckJoPVKgQ-jfWeJiALQRmnrgKzP51EXlmA3RYpi-gqB8KFC1cfJMJ-qATX3rXtkhPzZE-88JGw1D5rPzCEK_yS29n1-53rupux2RyKI7YQ4ucJFZDY7YcTuBBAg8WjQ99Edmey0QrfxEy0knTF7NhM?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/_RBuyuPXbR4hIA5h2tsbbxOSe8PDfSmoLgYt1UmgwLPOC0kMB5DBhuet4hwU5IpDLD1kCnUiKZ94fxMPW8BXlp3D2ZtgMbx25k2ySUQiOq8WgFqSt2eYcg18N1icW8TTn7wVHKzeG5htcoIXzpQPXeu1W9xve85DkQdIu5cdYMm5ng1peUOvkfHFmQaZnbHg?purpose=fullsize)

* Lower cost than Standard
* But charges when you access data
* Still fast retrieval

**Use case:**

* Backups
* Disaster recovery files

---

#### 4. S3 One Zone-IA

![Image](https://images.openai.com/static-rsc-4/gO3R6Xwhz8tQIBhC5HLCQ0D7o6Z0zHhnx6UBMDTP2yOAEGm5-QTPx32hClNJD2wm8JA1WAHkSn-sw5l9BULbM5Mcg61yh20yPKOaLGuCUcBgprMqheVEJ4jMOXvmUmWulwAb_jZVBNdUDDh7htsSTjIfO5owkVstpVKeKrP_34FS8vbfCfZ1ugM2rdULoA6y?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/Zf09y4jors4CiX4GwuxZet8MJZTRr1QwFOpwCUkH-dK0VJ1gRSint2ggC54QAS4bf6yNUwmh4vI_VRLI94Snyj0KcoL5Ihufa-P4koMxvpCtfT6A4CRuuSl4TYYrDFxwYt8cUpN-j3RHObjYrkUoaFkkT_JlyjdjeQw7_VTFktQa2K0nFxgo-cEaJGHATlml?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/b4XoPolFYMQ-dNJErbQMl0qdDupDJii7INTlYG7vT3Xho-1cg8t1479D6BqJCFWK1AflYR_VdmzqeCQvUdJesD1mPvES8BZ2-GVavD_olGYFSvT0KJJoiXLxz8eNyeUTzdg2D_YxMnLd3LYT9mVQLEvlZLOwKDHWE6KuKMsGvzPsM6kLVv8x2soiGfZboNwY?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/2q0DHG1WPdFK4NBP7oxyF-xpe9Qg54sqZMOelBmYG_vObGrG4B7Uf5pHPpPbtzORsbCwn0EN_ehnXpMxTEWGxOsOKcO8u8-xnaHLB1TloXy1_LLL9Be5TT6XvTWjDluGnWo-ZxINKrErIl1P9Z2osyT9-_CxdAlcyl55Nogl5C3gh9MvZqatbpmjtnmgD1Ld?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/QEPU0wFIpxG4Nhwk3cpH_GkSg-W5EzP6LeqvpdPzvbdDdTZcvI0BFLfHydS1IKkvwS2DcUkINX7Nvr3eI5Zah98hOYI_mRrFUgl0D-52wTUy0VqBh-D8xNa__v-FQlBbVPLw883UVHjf6ZvkHrAmw_g58Wpbyg1ydkFDWN3RoZbzVk9pxkiAlIHzQzDW_8qd?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/bJDoMFhRkLSleayyVLZ3nj8iSZQiziPPcTmq_DdJtllvQA-VVbuP56Bqw2Cs6NNnhySiybIsJSBYARsia3DzlCKiyXvVSVBY-n88D1nzus73v5bS8GX6CDr2mtqcTnCrzQxTPomkTTj98LFMsSLSZwkeOawT-wtGCMBQEfchZa-0hTFGA5M7yr0Gs40xvePY?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/ZeFbb_-gqlN053T9FNO0NQO-lhA4yLoqVaDyGHRQ4Jro2qEC9SjyiN-ZXoOUS47WffHtDMS7S0FvqM-9ZXmP_CaxABThA326KLYrg7JJRva6Q8RiEZEDWBp0oL8G_LC_-ZR-w3Z-4d68qBEY4Y5h940Ycviae4m5db69N1YED6Tvh60XcuS1SIOEMYDTVrj6?purpose=fullsize)

* Stored in only one AZ (cheaper)
* Risk of data loss if AZ fails

**Use case:**

* Re-creatable data
* Temporary backups

---

#### 5. S3 Glacier (Archive)

![Image](https://images.openai.com/static-rsc-4/a-vEO87dV_PNMcqdhu4-lFCwVayA074hUlwWKM2hTAEOrVcwyg-ED_KhixDQjH-mMGGxHdYqEv2QvSdA0faxq9Z63BzJi4k-llQAO8QO9MeECW0VZNPC_DEGGoy_OQnmZSUO6Q23Zv8K6HBh47jjW7pJ1OPdl8bu2HoGSmEXPenj3J2OKiavU5vxW_UkJuTa?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/rTvY3uUk6W3FvtHOo6iEYctXW-MtrlEkMxudCNUYgEqhDkjWttftgyqFr81xFduMJJbuydCTufpK2Y-0Ahnd3Inr4HocRlSaHL5Xv1FFQDQ1PSXrf8-fY0RvlgeF9YhX0nq7FVYZaGRj5zuSM-iMmnCD2_W-AFRXdr8m_ruEH_It3H3ex-6PaeAjTNpVYS8e?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/qy1rpXRvzfIS9fzhbZf7g9x4ZZcVK1j5KY6DxKSZLP_Pjugi4JzINZKZaiThw13ftJ6uFRjCwKz2LmJwOTmdhDAD6xgAiBrNH3yB7BNfBoNxZumBskAwd96vH4dcYoZhH-ncU-4TxKzqrahV3G6TWhFdann_L55xHrKWaK5L4lIYFJjKTOU0_2Ra2m1QC18B?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/BlGGHPPuP8wS7ZOPev9oonqD9HkVZ_3DvqhsZJN6oDqK4fQpMApj4WWIs8pc51Epqb2IHdY76jJ9Xho6AXvV71-KWbMlbtllt_lvmROlviuPA-7PPxrVvrOY0PF8k2fvJ2642rLOPFPxLd_dl7UYdzq735R9AyKN6j_65sVJNG7Tww6FZDol4mYGM-juy7tg?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/gk572kqEQJnN6VVa5duiQl7cg_sAGtwtGU11aor3-ZXjlpRJk9cNvihwIfzW2r7eVJmkxMMjD933VTpxj0j0TDLmVqD8iWHz2wvduXOkepiIMVrgPAtg4AG5Oh1VJvK0Wb-yKHkbTbUb-SgRtMtsuRIezTROcZkxajUALvqClHBSL7d-ZO1f6xrGjtUgrXDr?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/gQEOIXbmFD16kvAtS5pxQvBSL1hVMIF57rH0JpCRRw_fcEPYHa9PrasQvbwMQwcpIKOE4_el84fNnKJ0hKa0JcNrWmZvDgNqRRKkBr1dlEz9LiGROgANTb4_xl-kk-igfXbZGL_H-bafsKzbcb-sxMKVv80zi6V5zbhQZeAuiggdnd_ljunAUFo5GellXRLH?purpose=fullsize)

* Very low cost
* Retrieval takes minutes to hours

**Use case:**

* Old backups
* Compliance data

---

#### 6. S3 Glacier Deep Archive

![Image](https://images.openai.com/static-rsc-4/rTvY3uUk6W3FvtHOo6iEYctXW-MtrlEkMxudCNUYgEqhDkjWttftgyqFr81xFduMJJbuydCTufpK2Y-0Ahnd3Inr4HocRlSaHL5Xv1FFQDQ1PSXrf8-fY0RvlgeF9YhX0nq7FVYZaGRj5zuSM-iMmnCD2_W-AFRXdr8m_ruEH_It3H3ex-6PaeAjTNpVYS8e?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/qy1rpXRvzfIS9fzhbZf7g9x4ZZcVK1j5KY6DxKSZLP_Pjugi4JzINZKZaiThw13ftJ6uFRjCwKz2LmJwOTmdhDAD6xgAiBrNH3yB7BNfBoNxZumBskAwd96vH4dcYoZhH-ncU-4TxKzqrahV3G6TWhFdann_L55xHrKWaK5L4lIYFJjKTOU0_2Ra2m1QC18B?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/WYNvcgNTC6K73-_URXHQa83VAzs-M50lc2Vk0eVud82h4Evk4_V98s2KM9G88Dgz3EtHxHeQYMtEIiOCU-GaGXA2CmJ0JDOWpMRfaV3ERjHzKYdQfTCT4ImUL3W8TAZB7FaMi1mAW2bTYJkvC4ZgrIJkAVppH6QuEsgnD5ykxGzeiXVF8QkWw5DDgwR40i_0?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/q0oUP8NFn0sfzF7hxjLSrNzAJU0KTSJm7HERkOMomKntoljfv3Am76w_LYS_ULLZIqWnfsjbUGoImkvLNNFui62r6dBlpUylaZAs_IRJxccL3xklghe4DsHXDCYA5qDGruHGYLpq6SYjMGo6jS9kLZCqZoG80Q_NNKSuNFuyC7p1sasKcw7IH8m0UPWpPUTb?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/BlGGHPPuP8wS7ZOPev9oonqD9HkVZ_3DvqhsZJN6oDqK4fQpMApj4WWIs8pc51Epqb2IHdY76jJ9Xho6AXvV71-KWbMlbtllt_lvmROlviuPA-7PPxrVvrOY0PF8k2fvJ2642rLOPFPxLd_dl7UYdzq735R9AyKN6j_65sVJNG7Tww6FZDol4mYGM-juy7tg?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/0LV0xMRcUrp11p9FQNDvlgOhtXeOYrm6d0rAc_3UTrHaCH88KbhGKQ-mZuwsAxHVTXbAs0_f74TnXAKE7a32AJX6jychvyFEhDtZBzjq9WpSjLweXGE3jOcHEdZuZTCm_cCfz6Dw-rrzWkw7Bf8IUw5wMKYru41YXr9UpmFA95sLvzLqCUCVT8CtuuZNvsrS?purpose=fullsize)

* Cheapest storage option
* Retrieval takes hours (or more)

**Use case:**

* Data you almost never access
* Legal/financial archives

---

### Quick comparison

| Storage Class       | Cost       | Speed         | Best for          |
| ------------------- | ---------- | ------------- | ----------------- |
| Standard            | High       | Instant       | Active data       |
| Intelligent-Tiering | Medium     | Instant       | Unknown usage     |
| Standard-IA         | Lower      | Instant       | Rare access       |
| One Zone-IA         | Even lower | Instant       | Non-critical data |
| Glacier             | Very low   | Minutes–hours | Archive           |
| Deep Archive        | Lowest     | Hours         | Long-term storage |

---

### Simple way to choose

* Not sure? → **Intelligent-Tiering**
* Daily usage? → **Standard**
* Backup? → **Standard-IA**
* Archive? → **Glacier / Deep Archive**

---

### Real-world example (your project)

For something like your platform:

* User profile images → Standard
* Old invoices → Standard-IA
* Logs older than 3 months → Glacier
* 1+ year old data → Deep Archive

### Management Tools for data control

<img src="./src/s3/s3_management_tool_for_data_control.png" alt="Management Tools for data control"/>

### Data analytics and versioning



## Access Management
<img src="./src/s3/s3_access_management.png" alt="s3 access management"/>

**Access Management**, which in AWS is primarily handled by AWS Identity and Access Management (IAM).

### What is IAM?

IAM controls:

* **Who** can access AWS resources
* **What** actions they can perform
* **Which** resources they can access

Think of IAM as the security guard of your AWS account.

---

### IAM Components

#### 1. Users

Individual identities for people or applications.

Example:

* Jay
* Developer1
* AdminUser

A user can have:

* Password (AWS Console login)
* Access Keys (CLI/API access)

---

#### 2. Groups

A collection of users with similar permissions.

Example:

* Developers
* QA Team
* Administrators

Instead of assigning permissions to each user, assign them to a group.

---

#### 3. Policies

Policies define permissions using JSON.

Example policy allowing S3 read access:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "s3:GetObject"
      ],
      "Resource": "*"
    }
  ]
}
```

Policies answer:

* Allow or Deny?
* Which actions?
* On which resources?

---

#### 4. Roles

Roles provide temporary permissions.

Common examples:

* EC2 accessing S3
* Lambda accessing DynamoDB
* Cross-account access

Instead of storing credentials in code, AWS services assume roles.

---

### Authentication vs Authorization

| Concept        | Meaning          |
| -------------- | ---------------- |
| Authentication | Who are you?     |
| Authorization  | What can you do? |

Example:

* Login using username/password → Authentication
* Allowed to delete an S3 bucket → Authorization

<img src="./src/s3/s3_resource_based_policy.png" alt="resource based policy"/>

<img src="./src/s3/s3_user_policy.png" alt="user policy"/>


# AWS EC2: Elastic Compute Cloud

Amazon EC2 (Elastic Compute Cloud) is a service that provides virtual servers in the AWS cloud.

EC2 provides **virtual servers in the cloud**. Instead of buying a physical machine, you rent a server from AWS and run your applications on it.

<img src="./src/ec2/ec2_overview.png" alt="EC2 Overview"/>

## What is EC2?

Think of EC2 as a computer running in an AWS data center.

You can:

* Install Linux or Windows
* Run websites and APIs
* Host databases (though RDS is usually preferred)
* Run Docker containers
* Deploy FastAPI, Django, Node.js, etc.

EC2 allows you to:
- Run Linux or Windows servers
- Host websites
- Deploy APIs
- Run Docker containers
- Execute batch jobs
- Perform development and testing

Example:
```txt
Your Laptop
    ↓
Internet
    ↓
AWS EC2 Server
    ↓
Application
```

## EC2 Architecture
```txt
AWS Account
    ↓
VPC
    ↓
Subnet
    ↓
EC2 Instance
    ↓
EBS Volume
```

Every EC2 instance runs inside a VPC.

## EC2 Components

AWS EC2, is built using different components


### EC2 AMI (Amazon Machine Image)

An AMI is a template used to launch instances. It is like a template for your server.

Examples:
```txt
Ubuntu
Amazon Linux
Red Hat
Windows Server
```

<img src="./src/ec2/ec2_ami.png" alt="EC2 AMI"/>

### EC2 instance

We can create aws EC2 instances i.e. virtual system as per our requirement.

Determines CPU, RAM, and performance.

Examples:

| Instance  | vCPU     | Use Case         |
| --------- | -------- | ---------------- |
| t3.micro  | 2        | Small apps       |
| t3.small  | 2        | Development      |
| t3.medium | 2        | Medium workloads |
| c7g.large | More CPU | Compute-heavy    |
| r7g.large | More RAM | Memory-heavy     |

<img src="./src/ec2/ec2_instances.png" alt="EC2 Instances"/>

### EBS: Elastic Block Store

Amazon Elastic Block Store (EBS) is a persistent block storage service used with EC2 instances.

Your EC2 disk storage.
Like:
* SSD/HDD attached to a computer

Stores:
* OS
* Application code
* Logs

<img src="./src/ec2/ec2_ebs_overview.png" alt="AWS EBS Overview"/>
<img src="./src/ec2/ec2_ebs_performance.png" alt="AWS EBS Performance"/>
<img src="./src/ec2/ec2_ebs_ssd_storage.png" alt="AWS EBS SSD"/>
<img src="./src/ec2/ec2_ebs_hdd_storage.png" alt="AWS EBS HDD"/>

#### Security Groups

A firewall for EC2.

Example rules:

| Port | Purpose |
| ---- | ------- |
| 22   | SSH     |
| 80   | HTTP    |
| 443  | HTTPS   |
| 8000 | FastAPI |

If port 8000 isn't allowed, your FastAPI app won't be reachable.


#### Key Pair

Used for SSH access.

Example:

```bash
ssh -i mykey.pem ubuntu@<public-ip>
```

Keep the `.pem` file safe.


### Launch Flow

```text
AMI
 ↓
Instance Type
 ↓
Storage (EBS)
 ↓
Security Group
 ↓
Key Pair
 ↓
Launch EC2
```

---

### Example: Deploy FastAPI

1. Launch Ubuntu EC2
2. Open ports:

   * 22
   * 80
   * 443
3. SSH into server

```bash
ssh -i key.pem ubuntu@server-ip
```

4. Install Python

```bash
sudo apt update
sudo apt install python3-pip
```

5. Run FastAPI

```bash
uvicorn app:app --host 0.0.0.0 --port 8000
```

6. Access from browser

```text
http://server-ip:8000/docs
```

---

### Public IP vs Private IP

| Type       | Accessible From |
| ---------- | --------------- |
| Public IP  | Internet        |
| Private IP | Inside VPC      |

Example:

* Public: `13.x.x.x`
* Private: `172.31.x.x`

---

### EC2 Pricing Models

#### On-Demand

Pay as you use.

Best for:

* Development
* Testing

#### Reserved Instances

Commit for 1–3 years.

Best for:

* Predictable workloads

#### Spot Instances

Use spare AWS capacity.

Can be terminated anytime.

Best for:

* Batch jobs
* CI/CD

---

### Important EC2 Concepts

* Start Instance
* Stop Instance
* Reboot Instance
* Terminate Instance (deletes the server)
* Create AMI (server backup)
* Attach IAM Role
* Attach EBS Volume

---

### Real-world Architecture

For a FastAPI application:

```text
Users
   ↓
Load Balancer
   ↓
EC2 (FastAPI)
   ↓
RDS (PostgreSQL)
   ↓
S3 (Files/Images)
```

# AWS DNS: Domain Name System

DNS is a system, that translate human readable english domain name to a fixed IP, for server commnunication.

<img src="./src/dns/dns_overview.png" alt="AWS DNS>

<img src="./src/dns/dns_process.png" alt="AWS DNS Process>



