```vue
<template>
  <div class="col-xl-12 col-md-12">
    <div class="row mt-2 mb-5 pb-3 mx-2">
      <div class="card card-body mb-5">

        <h2 class="main-title">
          Technical Program Committee (Tentative)
        </h2>

        <div class="committee-grid">
          <div
            v-for="member in members"
            :key="member.name"
            class="member-card"
          >
            <img
              :src="getImage(member)"
              :alt="member.name"
              class="member-image"
            />

            <div class="member-content">
              <h5>{{ member.name }}</h5>
              <p>{{ member.organization }}</p>
            </div>
          </div>
        </div>

      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Technical_Committee",

  data() {
    return {
      members: [
        {
          name: "Prof. B. Bhattacharyya",
          organization: "IIT (ISM) Dhanbad"
        },
        {
          name: "Prof. Parimal Acharjee",
          organization: "NIT Durgapur"
        },
        {
          name: "Prof. P. K. Sadhu",
          organization: "IIT (ISM) Dhanbad"
        },
        {
          name: "Dr. Rupesh Wandhare",
          organization: "IIT Hyderabad"
        },
        {
          name: "Dr. Amit Kumar Jain",
          organization: "IIT Delhi"
        },
        {
          name: "Dr. Kalyan Chatterjee",
          organization: "IIT (ISM) Dhanbad"
        },
        {
          name: "Dr. Nitika Vats Doohan",
          organization: "SAGE University, Indore"
        },
        {
          name: "Dr. Shailendra Kumar Sharma",
          organization: "SGSITS, Indore"
        },
        {
          name: "Dr. Rohit Bhakar",
          organization: "MNIT Jaipur"
        },
        {
          name: "Dr. Srinivas Bhaskar Karanki",
          organization: "IIT Bhubaneswar"
        },
        {
          name: "Dr. O. H. Gupta",
          organization: "NIT Jamshedpur"
        },
        {
          name: "Dr. Papia Ray",
          organization: "VSSUT Burla"
        },
        {
          name: "Dr. Ritesh Keshri",
          organization: "VNIT Nagpur"
        },
        {
          name: "Dr. A. Kirubakaran",
          organization: "NIT Warangal"
        },
        {
          name: "Dr. B. Venugopal Reddy",
          organization: "NIT Warangal"
        },
        {
          name: "Dr. Ch. Ramulu",
          organization: "NIT Warangal"
        },
        {
          name: "Dr. Nishant Kumar",
          organization: "IIT Gandhinagar"
        },
        {
          name: "Dr. Aniruddha Bhattacharya",
          organization: "NIT Durgapur"
        },
        {
          name: "Dr. Ram Krishan",
          organization: "NIT Warangal"
        }
      ]
    };
  },

  methods: {
    getImage(member) {
      try {
        return require(
          `@/committee_images/technical_committee/${member.name}, ${member.organization}.png`
        );
      } catch (error) {
        return "";
      }
    }
  }
};
</script>

<style scoped>
.main-title {
  text-align: center;
  font-weight: 700;
  margin-bottom: 40px;
  color: #1f2937;
}

.committee-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
  gap: 24px;
}

.member-card {
  background: #ffffff;
  border-radius: 18px;
  overflow: hidden;
  box-shadow: 0 8px 25px rgba(0,0,0,0.08);
  transition: all 0.35s ease;
  border: 1px solid rgba(0,0,0,0.05);
  text-align: center;
}

.member-card:hover {
  transform: translateY(-8px);
  box-shadow: 0 16px 35px rgba(0,0,0,0.15);
}

.member-image {
  width: 100%;
  height: 280px;
  object-fit: contain;
  object-position: center;
  background: linear-gradient(135deg, #f8fafc, #e2e8f0);
  padding: 12px;
}

.member-content {
  padding: 18px;
  text-align: center;
}

.member-content h5 {
  font-size: 1rem;
  font-weight: 700;
  margin-bottom: 8px;
  color: #111827;
  line-height: 1.4;
}

.member-content p {
  margin: 0;
  color: #64748b;
  font-size: 0.9rem;
  line-height: 1.5;
}

@media (max-width: 992px) {
  .committee-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (max-width: 576px) {
  .committee-grid {
    grid-template-columns: 1fr;
  }

  .member-image {
    height: 280px;
  }
}
</style>
```
